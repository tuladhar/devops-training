# Personal DevOps 1-on-1 Training — Enrollment Challenge

Before new DevOps coaching enrollments are accepted, candidates must complete the following challenges.

## Operating System

Basic Linux (Ubuntu) tasks, relevant to DevOps:

- How much memory is free?
- How many CPU cores are available, and which process is consuming the most CPU?
- Is swap enabled or not?
- Install the package `nmap` from the package manager.
- How much disk space is available?
- How long (time) has this machine been up/running?

Challenge URL: https://labs.iximiuz.com/challenges/linux-basics-every-devops-needs-to-know-e8fcf935

## Programming

Basic challenges relevant to DevOps:

- Use any programming language to check if a website is up by reading the HTTP status code — confirm it's `200 OK` for `https://purutuladhar.com`.

## Bash

A sample log file containing a mix of `INFO`, `WARN`, and `ERROR` lines is provided at [`logs/app.log`](logs/app.log). Output only the `ERROR` log lines (hint: `grep`).

## Terminal Knowledge

- Run `ls -lh no-such-file.txt` (a file that does not exist) and show the exit status code. Then run `ls -lh README.md` and show that exit code too — explain why they differ.
- Create a directory tree in one command: a `devops` directory with subdirectories `linux` and `kubernetes` (hint: `mkdir -p`). Verify the structure with `tree devops`.
- In the `devops/linux` directory, create a file `kernel.txt` containing:
  - The current stable version of the Linux kernel, from https://www.keleases/
- Redirect and append: write the current date to `devops/current-date.txt` using `>`, then append your username (`whoami`) to the same file usinernel.org/
- In the `devops/kubernetes` directory, create a file `k8s.txt` containing:
  - The current latest version of Kubernetes, from https://kubernetes.io/rg `>>`.

## Git Version Control

- Install git and use the `clone` command to download a copy of the repository https://github.com/tuladhar/ssl-handshake.git. How many lines are in `main.go`?

## Container

- **Docker challenge:** Install Docker, check the installed version, and verify the Docker daemon is running.
- **Image challenge:** Pull the Nginx container image version 1.31 from `public.ecr.aws/nginx/nginx:1.31`, and check the image size.

## Networking & Protocols

- Find the IPv4 and IPv6 addresses of `kernel.org` using the `host` command. Output the addresses to `ipv4.txt` and `ipv6.txt`.
- Using `curl -v`, find when the HTTPS certificate for https://github.com was issued and when it expires.
- Send 5 ping requests to verify `google.com` is up (`ping -c 5 google.com`), and record the min/avg/max round-trip time in `max.txt`.

## Cloud Providers

- `aws.amazon.com` is the website for Amazon Web Services (AWS). What are the equivalent websites for Google Cloud Platform (GCP) and Microsoft Azure?

## Configuration Management

- **Ansible:** Install Ansible using the `apt` package manager, and report the installed version.
- **Terraform (IaC):** Download the Terraform binary from https://releases.hashicorp.com/terraform/1.15.8/terraform_1.15.8_linux_amd64.zip, extract it using `unzip`, and verify the version with `terraform version`. Write the size of the binary to `size.txt`.

## CI/CD

1. Create a GitHub account, and create a public repository called `cicd`.
2. Create `index.html` with the following content:

   ```
   My name is Your Name and I'm learning CI/CD pipeline.
   ```

3. Create a `Dockerfile` with the following content:

   ```dockerfile
   FROM nginx:alpine
   COPY index.html /usr/share/nginx/html/index.html
   ```

4. Create a directory `.github/workflows`, and inside it create `build.yaml`:

   ```yaml
   name: Build Docker

   on:
     push:
       branches: [main]

   jobs:
     build:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v4

         - name: Build Image
           run: docker build -t cicd:1.1 .
   ```

## Secrets Management

- Go to your repository settings and create an environment called `dev` (Settings → Environments → New environment).
- The environment currently has no secrets. Click "Add" to create a new secret:
  - `SECRET_NAME`: `ROOT_PASSWORD`
  - Value: `secret123`
