# CodingProblems

Solutions for coding questions from LeetCode

## MkDocs Material Docker

Download Docker image with the following command

```
docker pull squidfunk/mkdocs-material:7.1.9
```

Serve:

```
docker run --rm -it -p 8080:8000 -v /c/Users/пользователь/Documents/My-GitHub/CodingProblems/:/docs squidfunk/mkdocs-material 
```

Default Windows address will be <http://192.168.99.100:8080/>

Build:

```
docker run --rm -it -v %cd%:/docs squidfunk/mkdocs-material build
```

Deploy on GitHub Pages:

```
docker run --rm -it -v ~/.ssh:/root/.ssh -v %cd%:/docs squidfunk/mkdocs-material gh-deploy
```

[Usage tutorial](https://hub.docker.com/r/squidfunk/mkdocs-material/)
