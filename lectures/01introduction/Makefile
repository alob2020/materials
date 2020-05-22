SHELL := /bin/zsh

slides: slides.pdf

slides.pdf: slides.md
	(cat $<; echo "") \
	| sed -e $$'/^Note:/,/^$$/ s/^$$/:::\\\n/' \
	| sed -e '/^Note:/,/^$$/ s/^Note:/::: notes/'\
  | pandoc -t beamer -o $@

clean:
	rm slides.pdf