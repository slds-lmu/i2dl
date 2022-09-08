# README

- Directories and filenames have to be lowercase
- Chapters are ordered after filenames
- if no video is given or no pdf file is present: delete yaml param completely
- to include pdfs, use [pdfjs](https://github.com/anvithks/hugo-embed-pdf-shortcode): `{{< pdfjs file="slides-regression-losses.pdf" >}}`. The pdf has to be in the same directory as the md file.
  - if you point to an external pdf like `{{< pdfjs file="https://foo.bar/my.ppf" >}}` only a download button will be shown. PDFJS is not possible as [cors](https://enable-cors.org/) is blocked from most servers.
- if you add a markdown or html link to a file that is in the same directory
  - you should use the shortcode `{{< fileurl file="cheatsheet_notation.pdf" >}}` 
  - if you link to `../file.pdf` it will break in the index pages
- to include lecture video: `{{< video id = "Syrzezpj2FY" >}}`
  - the `video_id` is the last part of the youtube url, e.g. for `https://www.youtube.com/watch?v=BmSvhDCdJro` it is `BmSvhDCdJro`.
  - You can also embed videos from other platforms by changing `video_base_url` in `config.toml`
  - Or use a custom shortcode.
- mathjax
  - can be enabled globally per default in `config.toml`
  - if mathjax should be supported in index page, add it to respective `_index.md` or enable it in `config.toml`
  - on a per page level `mathjax: true` in yaml-frontmatter
  - Problem: If you want to use mathjax in quizdown you have to set `mathjax: false` in YAML header and you cannot use mathjax in other parts of the document :(
- make quizzes using https://github.com/bonartm/hugo-quiz
  - put `quizdown: true` in yaml-frontmatter
  - quizzes support mathjax without the `mathjax: true`
- in `_index.md` you can specify `show_in_index: (content|summary|none)`

## License

[MIT LICENSE](LICENSE)

- Theme for https://github.com/jakob-r/hugo-course
- Example on https://jakob-r.de/hugo-course
