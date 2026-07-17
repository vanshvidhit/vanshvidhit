import gen as G

DARK = G.theme_dark()
LIGHT = G.theme_light()

VAR_MAP = {
    "bg": "bg", "panel": "panel", "panel_op": "panel-op", "border": "border",
    "text": "text", "muted": "muted",
    "glow1": "glow1", "glow2": "glow2", "glow3": "glow3",
    "cursor": "cursor", "food": "food", "food_stroke": "food-stroke",
}

def var_theme():
    t = dict(name="single")
    for k, css in VAR_MAP.items():
        t[k] = "var(--{})".format(css)
    t["grad"] = ["var(--grad0)", "var(--grad1)", "var(--grad2)"]
    t["ascii_grad"] = ["var(--grad0)", "var(--grad1)"]  # not used for filter math here
    t["snake"] = ["var(--snake0)", "var(--snake1)"]
    return t


def css_block():
    def rules(t, indent=""):
        lines = [
            "{i}--bg:{bg};".format(i=indent, bg=t["bg"]),
            "{i}--panel:{panel};".format(i=indent, panel=t["panel"]),
            "{i}--panel-op:{op};".format(i=indent, op=t["panel_op"]),
            "{i}--border:{b};".format(i=indent, b=t["border"]),
            "{i}--text:{c};".format(i=indent, c=t["text"]),
            "{i}--muted:{c};".format(i=indent, c=t["muted"]),
            "{i}--grad0:{c};".format(i=indent, c=t["grad"][0]),
            "{i}--grad1:{c};".format(i=indent, c=t["grad"][1]),
            "{i}--grad2:{c};".format(i=indent, c=t["grad"][2]),
            "{i}--glow1:{c};".format(i=indent, c=t["glow1"]),
            "{i}--glow2:{c};".format(i=indent, c=t["glow2"]),
            "{i}--glow3:{c};".format(i=indent, c=t["glow3"]),
            "{i}--cursor:{c};".format(i=indent, c=t["cursor"]),
            "{i}--food:{c};".format(i=indent, c=t["food"]),
            "{i}--food-stroke:{c};".format(i=indent, c=t["food_stroke"]),
            "{i}--snake0:{c};".format(i=indent, c=t["snake"][0]),
            "{i}--snake1:{c};".format(i=indent, c=t["snake"][1]),
        ]
        return "\n".join(lines)

    css = []
    css.append(":root {\n" + rules(DARK, "  ") + "\n}")
    css.append("@media (prefers-color-scheme: light) {\n  :root {\n" + rules(LIGHT, "    ") + "\n  }\n}")
    css.append(".vlight { display: none; }")
    css.append("@media (prefers-color-scheme: light) {\n  .vdark { display: none; }\n  .vlight { display: inline; }\n}")
    return "<style>\n" + "\n".join(css) + "\n</style>"


def build_ascii_dual(vt):
    c0d, c1d = G.hex_to_rgb(DARK["ascii_grad"][0]), G.hex_to_rgb(DARK["ascii_grad"][1])
    c0l, c1l = G.hex_to_rgb(LIGHT["ascii_grad"][0]), G.hex_to_rgb(LIGHT["ascii_grad"][1])
    n = lambda c: tuple(v / 255.0 for v in c)
    c0dn, c1dn, c0ln, c1ln = n(c0d), n(c1d), n(c0l), n(c1l)

    box_x, box_y = 60, 84
    box_w, box_h = 364, 372
    img_ar = G._PORTRAIT_W / G._PORTRAIT_H
    box_ar = box_w / box_h
    if img_ar > box_ar:
        draw_w = box_w
        draw_h = box_w / img_ar
    else:
        draw_h = box_h
        draw_w = box_h * img_ar
    draw_x = box_x + (box_w - draw_w) / 2
    draw_y = box_y + (box_h - draw_h) / 2

    glow_id = "portraitGlow"
    defs_out = []

    def make_filter(fid, r0, r1, g0, g1, b0, b1):
        return (
            '<filter id="{fid}" x="-20%" y="-20%" width="140%" height="140%" color-interpolation-filters="sRGB">'
            '<feComponentTransfer>'
            '<feFuncR type="table" tableValues="{r0:.4f} {r1:.4f}"/>'
            '<feFuncG type="table" tableValues="{g0:.4f} {g1:.4f}"/>'
            '<feFuncB type="table" tableValues="{b0:.4f} {b1:.4f}"/>'
            '</feComponentTransfer>'
            '<feColorMatrix type="hueRotate" values="0">'
            '<animate attributeName="values" values="0;22;0;-22;0" dur="10s" repeatCount="indefinite"/>'
            '</feColorMatrix>'
            '</filter>'
        ).format(fid=fid, r0=r0, r1=r1, g0=g0, g1=g1, b0=b0, b1=b1)

    defs_out.append(make_filter("portraitDuoDark", c0dn[0], c1dn[0], c0dn[1], c1dn[1], c0dn[2], c1dn[2]))
    defs_out.append(make_filter("portraitDuoLight", c0ln[0], c1ln[0], c0ln[1], c1ln[1], c0ln[2], c1ln[2]))
    defs_out.append('<filter id="{gid}" x="-60%" y="-60%" width="220%" height="220%">'
                     '<feGaussianBlur stdDeviation="9"/></filter>'.format(gid=glow_id))

    defs_out.append('<clipPath id="portraitReveal"><rect x="{x:.1f}" y="{y2:.1f}" width="{w:.1f}" height="0">'
                     '<animate attributeName="height" values="0;{h:.1f}" begin="0.3s" dur="1.3s" '
                     'fill="freeze" calcMode="spline" keySplines="0.22 1 0.36 1"/>'
                     '<animate attributeName="y" values="{ybot:.1f};{y2:.1f}" begin="0.3s" dur="1.3s" '
                     'fill="freeze" calcMode="spline" keySplines="0.22 1 0.36 1"/>'
                     '</rect></clipPath>'.format(x=draw_x - 6, y2=draw_y - 6, w=draw_w + 12, h=draw_h + 12,
                                                  ybot=draw_y - 6 + draw_h + 12))
    defs_out.append('<clipPath id="portraitBounds"><rect x="{x:.1f}" y="{y:.1f}" width="{w:.1f}" height="{h:.1f}"/></clipPath>'
                     .format(x=draw_x, y=draw_y, w=draw_w, h=draw_h))
    defs_out.append('<image id="portraitSrc" href="data:image/png;base64,{b64}" '
                     'x="{x:.1f}" y="{y:.1f}" width="{w:.1f}" height="{h:.1f}"/>'
                     .format(b64=G._PORTRAIT_B64, x=draw_x, y=draw_y, w=draw_w, h=draw_h))

    body = []
    body.append('<g id="portraitArt">')
    body.append('<animateTransform attributeName="transform" type="translate" '
                'values="0,0; 0,-7; 0,0" dur="6.5s" repeatCount="indefinite" '
                'calcMode="spline" keySplines="0.45 0 0.55 1; 0.45 0 0.55 1"/>')
    body.append('<use href="#portraitSrc" filter="url(#{gid})" opacity="0.55" '
                'clip-path="url(#portraitReveal)"/>'.format(gid=glow_id))
    body.append('<use href="#portraitSrc" filter="url(#portraitDuoDark)" class="vdark" '
                'clip-path="url(#portraitReveal)"/>')
    body.append('<use href="#portraitSrc" filter="url(#portraitDuoLight)" class="vlight" '
                'clip-path="url(#portraitReveal)"/>')
    body.append('<rect x="{x:.1f}" y="{y:.1f}" width="{w:.1f}" height="3" fill="url(#scanGrad)" '
                'opacity="0.8" clip-path="url(#portraitBounds)">'
                '<animate attributeName="y" values="{y:.1f};{ybot:.1f}" dur="4s" begin="1.8s" repeatCount="indefinite"/>'
                '</rect>'.format(x=draw_x, y=draw_y, w=draw_w, h=draw_h, ybot=draw_y + draw_h))
    body.append('<rect x="{x:.1f}" y="{y:.1f}" width="{w:.1f}" height="{h:.1f}" fill="none" '
                'stroke="url(#pillGrad)" stroke-width="1.2" opacity="0.7" rx="4"/>'
                .format(x=draw_x, y=draw_y, w=draw_w, h=draw_h))
    body.append('<rect x="{x:.1f}" y="{y2:.1f}" width="10" height="16" fill="var(--cursor)">'
                '<animate attributeName="opacity" values="1;1;0;0" keyTimes="0;0.5;0.51;1" '
                'dur="1s" begin="1.6s" repeatCount="indefinite"/>'
                '</rect>'.format(x=draw_x, y2=draw_y + draw_h + 6))
    body.append('</g>')

    return "\n".join(defs_out), "\n".join(body)


def build_svg_single():
    vt = var_theme()
    grad = vt["grad"]
    snake_grad = vt["snake"]
    defs = []
    defs.append('<linearGradient id="asciiGrad" x1="0%" y1="0%" x2="100%" y2="100%">'
                '<stop offset="0%" stop-color="var(--grad0)"/>'
                '<stop offset="100%" stop-color="var(--grad1)"/>'
                '</linearGradient>')
    defs.append('<linearGradient id="pillGrad" x1="0%" y1="0%" x2="100%" y2="0%">'
                '<stop offset="0%" stop-color="{a}"/><stop offset="50%" stop-color="{b}"/>'
                '<stop offset="100%" stop-color="{c}"/>'
                '<animateTransform attributeName="gradientTransform" type="translate" '
                'values="-1 0; 1 0; -1 0" dur="5s" repeatCount="indefinite"/>'
                '</linearGradient>'.format(a=grad[0], b=grad[1], c=grad[2]))
    defs.append('<linearGradient id="snakeBodyGrad" x1="0%" y1="0%" x2="100%" y2="100%">'
                '<stop offset="0%" stop-color="{a}"/><stop offset="100%" stop-color="{b}"/>'
                '</linearGradient>'.format(a=snake_grad[0], b=snake_grad[1]))
    defs.append('<linearGradient id="scanGrad" x1="0%" y1="0%" x2="100%" y2="0%">'
                '<stop offset="0%" stop-color="{c}" stop-opacity="0"/>'
                '<stop offset="50%" stop-color="{c}" stop-opacity="0.55"/>'
                '<stop offset="100%" stop-color="{c}" stop-opacity="0"/>'
                '</linearGradient>'.format(c=vt["glow2"]))
    defs.append('<linearGradient id="borderShimmer" x1="0%" y1="0%" x2="100%" y2="0%">'
                '<stop offset="0%" stop-color="{a}" stop-opacity="0"/>'
                '<stop offset="50%" stop-color="{b}" stop-opacity="0.9"/>'
                '<stop offset="100%" stop-color="{c}" stop-opacity="0"/>'
                '<animate attributeName="x1" values="-20%;120%" dur="4.5s" repeatCount="indefinite"/>'
                '<animate attributeName="x2" values="80%;220%" dur="4.5s" repeatCount="indefinite"/>'
                '</linearGradient>'.format(a=grad[0], b=grad[1], c=grad[2]))
    defs.append('<filter id="softGlow" x="-60%" y="-60%" width="220%" height="220%">'
                '<feGaussianBlur stdDeviation="2.1" result="blur"/>'
                '<feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>'
                '</filter>')
    defs.append('<filter id="bigGlow" x="-80%" y="-80%" width="260%" height="260%">'
                '<feGaussianBlur stdDeviation="6"/></filter>')
    defs.append('<clipPath id="canvasClip"><rect x="0" y="0" width="{w}" height="{h}" rx="26"/></clipPath>'
                .format(w=G.W, h=G.H))
    defs.append('<filter id="noiseFilter"><feTurbulence type="fractalNoise" baseFrequency="0.85" '
                'numOctaves="2" stitchTiles="stitch" result="noise"/>'
                '<feColorMatrix in="noise" type="matrix" values="0 0 0 0 1  0 0 0 0 1  0 0 0 0 1  0 0 0 0.02 0"/>'
                '</filter>')
    ascii_defs, ascii_body = build_ascii_dual(vt)
    defs.append(ascii_defs)

    parts = []
    parts.append('<svg width="{w}" height="{h}" viewBox="0 0 {w} {h}" '
                  'xmlns="http://www.w3.org/2000/svg">'.format(w=G.W, h=G.H))
    parts.append(css_block())
    parts.append('<defs>{}</defs>'.format("\n".join(defs)))
    parts.append('<g clip-path="url(#canvasClip)">')
    parts.append(G.build_background(vt))
    parts.append('<rect x="0" y="0" width="{w}" height="{h}" filter="url(#noiseFilter)"/>'.format(w=G.W, h=G.H))

    parts.append('<rect x="34" y="60" width="410" height="426" rx="18" fill="var(--panel)" fill-opacity="var(--panel-op)" '
                  'stroke="var(--border)" stroke-width="1"/>')
    parts.append(ascii_body)
    parts.append(G.build_terminal(vt))
    parts.append(G.build_snake(vt))

    parts.append('<rect x="1" y="1" width="{w2}" height="{h2}" rx="25" fill="none" '
                  'stroke="var(--border)" stroke-width="1.4"/>'.format(w2=G.W - 2, h2=G.H - 2))
    parts.append('<rect x="1" y="1" width="{w2}" height="{h2}" rx="25" fill="none" '
                  'stroke="url(#borderShimmer)" stroke-width="1.6"/>'.format(w2=G.W - 2, h2=G.H - 2))

    parts.append('</g>')
    parts.append('</svg>')
    return "\n".join(parts)


if __name__ == "__main__":
    svg = build_svg_single()
    with open("/home/claude/svg/banner.svg", "w") as f:
        f.write(svg)
    print("banner.svg", len(svg))
