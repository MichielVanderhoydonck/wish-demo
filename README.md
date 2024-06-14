# WishDemo

Just a tiny project to play around with [Wish by Charm_](https://github.com/charmbracelet/wish).  
The project's `Containerfile` can be used as a sandbox for building and running the app.

## Building
Using Docker  
`docker build -t wish -f Containerfile .`  
or Podman  
`podman build -t wish .`

## Running
Using Docker (similar for Podman)  
`docker run -v ./.ssh:/app/.ssh/ -it --rm --network=host -p 23234:23234 --name wish wish`  
(note that the network part was done for being able to work with docker running in Colima on an M2 Mac)

## Connecting

Current implementation uses password instead of other variants.  
`ssh -o PreferredAuthentications=password -o "UserKnownHostsFile=/dev/null" -p 23234 localhost`  
[Example other auth](https://github.com/charmbracelet/wish/blob/main/examples/multi-auth/main.go)

## TODO
I plan to better structure this project and try out some TUI flows learning the charm stack.