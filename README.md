# Feed-The-Beast Interactions (Modded Minecraft 1.12) in Docker
To pull the image:
```
docker pull audiohacked/ftb_interactions:stable
```

It's highly recommended run a named data volume:
```
docker volume create minecraft_ftb_interactions_data
docker volume create minecraft_ftb_interactions_backups
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_interactions \
    --volume minecraft_ftb_interactions_data:/minecraft/world \
    --volume minecraft_ftb_interactions_backups:/minecraft/backups \
    --publish 25565:25565 \
    --env EULA=TRUE \
    audiohacked/ftb_interactions:stable
```
