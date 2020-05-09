# Git-review Web UI

This repository contains a web UI for git-review reviews.

## Disclaimer

This is not an official Google product.

## Prerequisites

Building requires the Go tools and GNU Make. Running the built binary requires the git command line tool.

## Building the source code

Assuming you have the [Go tools installed](https://golang.org/doc/install), run
the following command:

    go get github.com/ajzaff/git-review-web/git-review-web

### Manual steps

Assuming you have not run the above command, first checkout the code from the git repo:

    mkdir -p ${GOPATH}/src/github.com/ajzaff
    cd ${GOPATH}/src/github.com/ajzaff
    git clone https://github.com/ajzaff/git-review-web.git

Build the binary:

    cd ${GOPATH}/src/github.com/ajzaff/git-review-web
    go install ./git-review-web/git-review-web.go

## Running the application

Binary is placed into `${GOPATH}/bin`:

    ${GOPATH}/bin/git-review-web

The tool requires that it be started in a directory that contains at least one git repo, and it shows the
reviews from every git repo under that directory.

With `git-review` installed, try `git review web --port 12345`

The UI is a webserver which defaults to listening on port 8080. To use a different port, pass it as an argument to the "--port" flag:

    ${GOPATH}/bin/git-review-web --port=12345