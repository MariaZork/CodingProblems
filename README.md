# CodingProblems

Solutions for coding questions from LeetCode

## MkDocs Material Docker (Windows)

Download Docker image with the following command

```
docker pull squidfunk/mkdocs-material:7.1.9
```

Build your custom Docker image with plugins:

```
docker build -f Dockerfile --tag mkdocs_custom .
```

Build:

```
docker run --rm -it -v /c/Users/пользователь/Documents/My-GitHub/CodingProblems/:/docs mkdocs_custom build
docker run --rm -it -v $(PWD):/docs mkdocs_custom build
```

Serve:

```
docker run --rm -it -p 8080:8000 -v /c/Users/пользователь/Documents/My-GitHub/CodingProblems/:/docs mkdocs_custom
docker run --rm -it -p 8080:8000 -v $(PWD):/docs mkdocs_custom
```

Default Windows address will be <http://192.168.99.100:8080/>

Deploy on GitHub Pages:

```
docker run --rm -it -v /c/Windows/System32/OpenSSH/:/root/.ssh -v /c/Users/пользователь/Documents/My-GitHub/CodingProblems/:/docs mkdocs_custom gh-deploy
 docker run --rm -it -v ~/.ssh:/root/.ssh -v ${PWD}:/docs mkdocs_custom gh-deploy
```

[Usage tutorial](https://hub.docker.com/r/squidfunk/mkdocs-material/)
