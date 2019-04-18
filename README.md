# My bash docker aliases

## Inspired By
https://github.com/tcnksm/docker-alias

## How to include
Edit file `.bash_profile` and add this:
```
if [ -f ~/.docker_aliases ]; then
    . ~/.docker_aliases
fi
```

## Docker Aliases
Then, create `.docker_aliases` and put this content:
```
# Docker alias
alias dk="docker"

# Get latest container ID
alias dkl="docker ps -l -q"

# Get container process
alias dkps="docker ps"

# Get process included stop container
alias dkpsa="docker ps -a"

# Get images
alias dki="docker images"

# Get images, filter via grep
dkif() { docker images | grep $1; }

# Stop all containers
dkstop() { docker stop $(docker ps -a -q); }

# Remove all containers
dkrm() { docker rm $(docker ps -a -q); }

# Stop and Remove all containers
alias dkrmf='docker stop $(docker ps -a -q) && docker rm $(docker ps -a -q)'
```

