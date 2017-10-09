# Latexmk inside of docker
## Usage
If you do not want to install all latex stuff on your machine and have docker installed you can use this image to build pdf files with latex.

```
docker pull janicmikes/latexmk
```

Navigate to your directory (this will be $(pwd) or %cd%)

UNIX Systems / Windows (PowerShell)
```
docker run --rm --mount type=bind,source="$(pwd)",target=/doc janicmikes/latexmk [LATEXMK-OPTIONS] TEX-FILENAME
```

Example for a Main.tex file that should compiled using xelatex:
```
docker run --rm --mount type=bind,source="$(pwd)",target=/doc janicmikes/latexmk -xelatex Main
```


Windows CMD
```
docker run --rm --mount type=bind,source="%cd%",target=/doc janicmikes/latexmk [LATEXMK-OPTIONS] TEX-FILENAME
```


## To build the docker image
Clone this Repository and build the image yourself with this command.
This should result in the same as the pull command, but you can be confident what is inside of your container.
```
docker build -t janicmikes/latexmk .
```

