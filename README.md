# imbercast.com

Placeholder site for Imbercast, a 3D sprinkler design and hydraulic calculation
desktop application. Static, single page, no build step and no dependencies.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole site. All CSS, JS and the isometric artwork are inline. |
| `favicon.svg` | Tab icon. |
| `og.png` | 1200x630 social preview, used by the Open Graph tags. |
| `CNAME` | Tells GitHub Pages the site is served at `imbercast.com`. |
| `.nojekyll` | Skips Jekyll processing. |

## Preview locally

Open `index.html` in a browser, or serve it:

```
python3 -m http.server 8000
```

Then visit http://localhost:8000.

## Signup form

The launch-list signup form was removed for now. It lived in the hero, above the
artwork, and posted to a third-party form service. To bring it back, restore the
form markup, its CSS section and its submit handler from git history, then point
the form action at a real endpoint.

## Publishing on GitHub Pages

Push this directory to a repository, then in the repo go to
**Settings > Pages** and set the source to the `main` branch, root folder.
Under **Custom domain** enter `imbercast.com` and save. Once the certificate
is issued, tick **Enforce HTTPS**.

## DNS at your registrar

For the apex domain `imbercast.com`, four A records:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

And, if your registrar supports IPv6, four AAAA records:

```
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```

For `www.imbercast.com`, one CNAME record pointing at `<your-username>.github.io`
with no repository name on the end.

DNS usually takes anywhere from a few minutes to a few hours to propagate.
GitHub Pages will show the domain as unverified until it resolves.

## Palette

| Token | Value | Used for |
| --- | --- | --- |
| `--accent` | `#4d9fff` | Wordmark, rule, button, sprinkler heads |
| `--red` | `#ff5c4a` | Eyebrow, status dot, capability numerals, logo core |
| pipe gradient | `#ff7264` to `#a82a1c` | Sprinkler piping in the artwork |

Pipe is red and the heads are flat blue, matching how sprinkler piping reads on
a drawing. The artwork has no glow on the heads. Red background washes sit under
the artwork and along the bottom of the page.

## Notes

Fonts come from Google Fonts (Space Grotesk, Inter, JetBrains Mono). Everything
else is self-contained, so the page works offline apart from the typefaces
falling back to system equivalents.
