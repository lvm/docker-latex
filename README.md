# docker-latex

A container for [LaTeX](https://latex-project.org/), a document preparation system for high-quality typesetting.

# how to 

## install

```bash
$ docker pull lvm23/latex
```

or 

```bash
$ git clone https://github.com/lvm/docker-latex && \
  cd docker-latex && \
  docker build -t latex .
```

## run

```bash
$ docker run -it -v $HOME/docs:/docs --name docs latex
```
  

`-v $HOME/docs:/docs` is used to mount the container's `/docs` directory to the host `$HOME/docs` directory, you can choose other directory.    

## build a `.tex` document? 

I didn't defined an `ENTRYPOINT` nor `CMD` on purpose, to leave the convertion open to the user.   
Anyway:  

`$ docker run -it -v $HOME/docs:/docs --name docs latex pdflatex document.tex`

Keep in mind that `document.tex` should be inside `$HOME/docs` which would be mounted in the containers `VOLUME` (ie: `/docs`)
