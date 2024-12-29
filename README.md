# Dockerfile Bug: Non-existent file in CMD instruction

This repository demonstrates a common error in Dockerfiles: attempting to execute a command that references a file or directory that doesn't exist within the image's filesystem.  The bug is in the `CMD` instruction, which tries to run a Python script that hasn't been copied into the image.

## Bug

The `DockerfileBug.dockerfile` contains the flawed Dockerfile.  It attempts to run `/app.py`, but this file is never copied into the image.

## Solution

The `DockerfileSolution.dockerfile` corrects the error by adding a `COPY` instruction to place the script within the image's filesystem, making it accessible to the `CMD` instruction.

This highlights the importance of carefully managing files and paths within a Docker image to ensure that commands can access the necessary resources.