# Assignment – Docker Fundamentals

## Overview

In this assignment, you will apply what you learned in **Lecture 2 – Leveraging Docker** by writing multiple Dockerfiles with different requirements and running them as **one-off containers**. Each container will perform a single task, print output to the terminal, and then exit.

You will build images, run containers, inspect container behavior, and actively manage Docker artifacts using the Docker CLI. The goal is not just to “get output,” but to develop a clear understanding of how Dockerfile instructions translate into images, how images become containers, and how Docker tracks and manages those resources.

All containers in this assignment should be treated as **disposable**.

---

## Assignment Structure

You will complete **four Docker tasks**, each increasing slightly in complexity. Each task should live in its own directory and contain its own Dockerfile.

Suggested folder structure:

```txt
docker-assignment/
├── task-1-hello/
├── task-2-file-read/
├── task-3-env-vars/
└── task-4-script/
```

---

## Task 1 – One-Off Command Container

### Goal

Create a Docker container that prints a custom message to the terminal and exits.

### Requirements

* Use `alpine` as the base image
* The container must run a **single command**
* The output must appear in the terminal
* The container must exit immediately after execution

### Steps

1. Create a directory named `task-1-hello`
2. Inside it, create a `Dockerfile`
3. Write a Dockerfile that prints a message of your choosing
4. Build the image and tag it appropriately
5. Run the container using `--rm`
6. Verify the output appears in your terminal

### End-State

* A working Dockerfile
* Terminal output showing the message
* Confirmation that no stopped containers remain

---

## Task 2 – Reading a File Inside a Container

### Goal

Create a container that reads and prints the contents of a text file that is included in the image at build time.

### Requirements

* Create a text file locally
* Copy the file into the image using `COPY`
* Use `WORKDIR`
* Use a command that prints the file’s contents
* Container must exit after execution

### Steps

1. Create a directory named `task-2-file-read`
2. Add a text file with any content
3. Write a Dockerfile that:

   * Sets a working directory
   * Copies the file into the image
   * Prints the file contents
4. Build the image
5. Run the container using `--rm`
6. View the output in the terminal

### End-State

* Dockerfile
* Text file
* Terminal output showing file contents

---

## Task 3 – Environment Variables Inside Containers

### Goal

Demonstrate how environment variables can be defined and accessed inside a container.

### Requirements

* Use an environment variable inside the container
* Print the value of that variable
* No interactive containers
* Container must exit after execution

### Steps

1. Create a directory named `task-3-env-vars`
2. Write a Dockerfile that:

   * Defines an environment variable
   * Prints the value of that variable
3. Build the image
4. Run the container using `--rm`
5. Observe the output

### Stretch (Optional)

* Override the environment variable at runtime using a Docker flag

### End-State

* Dockerfile
* Terminal output showing the environment variable value

---

## Task 4 – Running a Script Inside a Container

### Goal

Run a small script inside a container and print output to the terminal.

### Requirements

* Create a script file locally (shell or Python)
* Copy the script into the image
* Ensure the script executes when the container runs
* Container must exit after execution

### Steps

1. Create a directory named `task-4-script`
2. Write a script that prints multiple lines
3. Write a Dockerfile that:

   * Copies the script into the image
   * Executes the script
4. Build the image
5. Run the container using `--rm`
6. Confirm all script output appears in the terminal

### End-State

* Script file
* Dockerfile
* Terminal output

---

## Docker Resource Management Checklist

Throughout this assignment, you are expected to actively manage Docker artifacts.

At minimum, you should demonstrate:

* Viewing running containers
* Viewing all containers (including stopped)
* Removing stopped containers
* Listing images
* Removing unused images

You should be able to answer the following by the end:

* Why don’t stopped containers appear with `docker ps`?
* Why can’t an image be deleted if a container depends on it?
* What does the `--rm` flag prevent?

---

## Key Takeaway

This assignment is not about memorizing commands—it’s about developing confidence in Docker’s lifecycle. By intentionally building, running, inspecting, and cleaning up containers, you are practicing the exact workflow used daily in professional software engineering environments.

If Docker feels repetitive here, that’s the point.
