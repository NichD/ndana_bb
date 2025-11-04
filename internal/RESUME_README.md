Resume build call.

```bash
pandoc ndana_resume.md -o ndana_resume.pdf --pdf-engine=xelatex \
  -V geometry:top=0.6in,bottom=0.7in,left=0.7in,right=0.7in \
  -V fontsize=11pt \
  -V mainfont="Helvetica Neue" \
  -V linestretch=0.95 \
  -V parskip=2pt \
  -V titlepage=false
```
