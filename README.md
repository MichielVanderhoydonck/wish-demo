# WishDemo

## Building
Using Docker  
`docker build -t wish -f Containerfile .`  
or Podman  
`podman build -t wish .`

## Running
Using Docker (similar for Podman)  
`docker run -v ./.ssh:/app/.ssh/ --network=host -p 23234:23234 --name wish wish`  
(note that the network part was done for being able to work with docker running in Colima on an M2 Mac)

## Connecting

Current implementation uses password instead of other variants.  
`ssh -o PreferredAuthentications=password -p 23234 localhost`  
[Example other auth](https://github.com/charmbracelet/wish/blob/main/examples/multi-auth/main.go)

## TODO
I plan to better structure this project and try out some TUI flows learning the charm stack.