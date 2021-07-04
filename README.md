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

Serve:

```
docker run --rm -it -p 8080:8000 -v /c/Users/пользователь/Documents/My-GitHub/CodingProblems/:/docs mkdocs_custom
```

Default Windows address will be <http://192.168.99.100:8080/>

Build:

```
docker run --rm -it -v /c/Users/пользователь/Documents/My-GitHub/CodingProblems/:/docs mkdocs_custom build
```

Deploy on GitHub Pages:

```
docker run --rm -it -v /c/Windows/System32/OpenSSH/:/root/.ssh -v /c/Users/пользователь/Documents/My-GitHub/CodingProblems/:/docs mkdocs_custom gh-deploy
```

[Usage tutorial](https://hub.docker.com/r/squidfunk/mkdocs-material/)
