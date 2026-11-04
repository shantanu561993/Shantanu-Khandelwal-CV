# Shantanu Khandelwal — CV

LaTeX source for my résumé, built reproducibly with LuaLaTeX
([Awesome CV](https://github.com/posquit0/Awesome-CV) base, locally patched —
see `awesome-cv.cls` header comments).

## Structure

- `resume.tex` — main document (metadata, tag-PDF config, layout macros)
- `resume/*.tex` — content sections
- `awesome-cv.cls` — class; three local patches, documented inline
- `fonts/` — embedded typefaces
- `coverletter.tex` — cover letter skeleton

## Build locally

```bash
docker run --rm -v "%cd%:/work" -w /work texlive/texlive lualatex -interaction=nonstopmode resume.tex
```

Run twice; or any Te Live 2023+ / `latexmk -lualatex resume.tex`.

## CI & releases

`.github/workflows/build.yml` compiles on every push to `main` and on `v*` tags
(manual runs via Actions → Build CV PDF). The PDF is uploaded as a build
artifact; tag pushes attach it to a GitHub Release — see **Releases**.

The PDF is a tagged/accessible document (PDF/UA machinery via LaTeX
`\DocumentMetadata`): semantic headings/lists/tables, `ActualText` ASCII
replacements for decorative glyphs, copy-paste-clean extraction.

## License

CV content © Shantanu Khandelwal. Template parts CC BY-SA 4.0 —
© Claud D. Park / posquit0, https://github.com/posquit0/Awesome-CV
