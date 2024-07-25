# Articles: Production-ready Docker packaging for Python developers

#### Table of Contents

- [The basics of Docker packaging](https://pythonspeed.com/docker/#the-basics-of-docker-packaging)
- [Best practices for production](https://pythonspeed.com/docker/#best-practices-for-production)
    - [The broken status quo](https://pythonspeed.com/docker/#the-broken-status-quo)
    - [Base image and dependencies](https://pythonspeed.com/docker/#base-image-and-dependencies)
    - [Security](https://pythonspeed.com/docker/#security)
    - [Fast builds, small images](https://pythonspeed.com/docker/#fast-builds-small-images)
    - [Conda](https://pythonspeed.com/docker/#conda)
    - [Applications and runtime](https://pythonspeed.com/docker/#applications-and-runtime)
    - [Packaging as a process](https://pythonspeed.com/docker/#packaging-as-a-process)
    - [Docker variants and alternatives](https://pythonspeed.com/docker/#docker-variants-and-alternatives)

## [](https://pythonspeed.com/docker/#the-basics-of-docker-packaging)The basics of Docker packaging

1. [**Connection refused? Docker networking and how it impacts your image**](https://pythonspeed.com/articles/docker-connection-refused/)  
    Learn how to fix connection refused errors when trying to connect to a Docker container.
    
2. [**Faster or slower: the basics of Docker build caching**](https://pythonspeed.com/articles/docker-caching-model/)  
    Docker’s layer caching can speed up your image build—if you write your Dockerfile correctly.
    
3. [**Where’s that log file? Debugging failed Docker builds**](https://pythonspeed.com/articles/debugging-docker-build/)  
    Your Docker build just failed, and the reason is buried a log file—which is somewhere inside the build process. How do you read that log file?
    
4. [**Debugging ImportError and ModuleNotFoundErrors in your Docker image**](https://pythonspeed.com/articles/importerror-docker/)  
    There are many reasons your Python code might fail to import in Docker. Here’s a quick series of checks you can do to figure out the problem.
    
5. [**A tableau of crimes and misfortunes: the ever-useful `docker history`**](https://pythonspeed.com/articles/docker-history/)  
    Use the `docker history` command to understand how a Docker image is constructed, why an image is too big, and how Dockerfile commands work.
    

Looking for more? Learn the fundamental concepts of Docker packaging in just one afternoon, by reading my book: [Just Enough Docker Packaging](https://pythonspeed.com/products/justenoughdockerpackaging/).

## Best practices for production

### [](https://pythonspeed.com/docker/#the-broken-status-quo)The broken status quo

1. [**Broken by default: why you should avoid most Dockerfile examples**](https://pythonspeed.com/articles/dockerizing-python-is-hard/)  
    Most Dockerfile examples for Python you’ll find on the Web are broken. And that’s a problem.
    
2. [**Reviewing the official Dockerfile best practices: good, bad, insecure**](https://pythonspeed.com/articles/official-docker-best-practices/)  
    The official Docker documentation’s Dockerfile best practices are mostly good—but they are sometimes wrong, and if you’re using Python, too generic.
    
3. [**The worst so-called “best practice” for Docker**](https://pythonspeed.com/articles/security-updates-in-docker/)  
    Many people (although fewer than in the past) will tell you not to install security updates in your Docker image. This is terrible advice.
    

### [](https://pythonspeed.com/docker/#base-image-and-dependencies)Base image and dependencies

1. [**The best Docker base image for your Python application (May 2024)**](https://pythonspeed.com/articles/base-image-python-docker-images/)  
    Ubuntu? Official Python images? Alpine Linux? Here’s how to choose a good base Docker image for your Python application container.
    
2. [**A deep dive into the “official” Docker image for Python**](https://pythonspeed.com/articles/official-python-docker-image/)  
    The “official” Python Docker image is useful, but to actually understand why, and to use it correctly, it’s worth understanding how exactly it’s constructed.
    
3. [**Why you should upgrade pip, and how to do it**](https://pythonspeed.com/articles/upgrade-pip/)  
    Learn the problem with using old pip, and how to upgrade pip to fix those problems.
    
4. [**Using Alpine can make Python Docker builds 50× slower**](https://pythonspeed.com/articles/alpine-docker-python/)  
    Alpine Linux is often recommended as a smaller, faster Docker base image. But if you’re using Python, it will slow down your build and make your image larger.
    
5. [**When should you upgrade to Python 3.12?**](https://pythonspeed.com/articles/upgrade-python-3.12/)  
    Python 3.12 has been released—when should you switch to using it?
    
6. [**Building on solid ground: reproducible Docker builds for Python**](https://pythonspeed.com/articles/reproducible-docker-builds-python/)  
    Learn how to get reproducible Docker builds for your Python application, including base image, system packages, and Python dependencies.
    
7. [**It’s time to stop using Python 3.7**](https://pythonspeed.com/articles/stop-using-python-3.7/)  
    Python 3.7 will stop getting security updates in July 2023. Given the existence of 3.8, 3.9, 3.10, and 3.11, you really should upgrade.
    
8. [**CentOS 8 is dead: choosing a replacement Docker image**](https://pythonspeed.com/articles/centos-8-is-dead/)  
    CentOS 8 is no longer being maintained as a drop-in replacement for RedHat Enterprise Linux. Here are your options for replacing it as a Docker image.
    
9. [**Push and pull: when and why to update your dependencies**](https://pythonspeed.com/articles/when-update-dependencies/)  
    When should you update your software project’s dependencies? There are two rhythms to updates: security and critical bug fixes, and broader updates.
    
10. [**“Externally managed environments”: when PEP 668 breaks pip**](https://pythonspeed.com/articles/externally-managed-environment-pep-668/)  
    Getting a externally-managed-environment/PEP 668 error when you pip install? Here’s how to fix it.
    

### [](https://pythonspeed.com/docker/#security)Security

1. [**Installing system packages in Docker with minimal bloat**](https://pythonspeed.com/articles/system-packages-docker/)  
    Learn how to minimize your Docker image size while installing or updating system packages on on Debian, Ubuntu, and RHEL.
    
2. [**Avoiding insecure images from Docker build caching**](https://pythonspeed.com/articles/docker-cache-insecure-images/)  
    Docker’s layer caching is great for speeding up builds—but you need to be careful or it’ll cause you to have insecure dependencies.
    
3. [**Less capabilities, more security: preventing Docker escalation attacks**](https://pythonspeed.com/articles/root-capabilities-docker-security/)  
    Reduce the security risk from your Docker image by running as a non-root user and reducing capabilities.
    
4. [**Staying secure by breaking Docker caching**](https://pythonspeed.com/articles/disabling-docker-caching/)  
    Even more ways you can ensure Linux distribution security updates in the face of Docker caching.
    
5. [**How to (not) use Docker to share your password with hackers**](https://pythonspeed.com/articles/leaking-secrets-docker/)  
    Docker images can leak runtime secrets, build secrets, and even just some secret files you have lying around. Learn how to leak them, and how to avoid it.
    
6. [**Don’t leak your Docker image’s build secrets**](https://pythonspeed.com/articles/docker-build-secrets/)  
    When you’re building Docker images you often need some secrets: a password, an SS Hkey. The secure mechanism is BuildKit; others might leak them.
    
7. [**Build secrets in Docker and Compose v1, the secure way**](https://pythonspeed.com/articles/build-secrets-docker-compose/)  
    Builds secrets like passwords may be used to build your Docker image; learn how to use them securely in Docker Compose without leaking them.
    
8. [**Finding leaked secrets in your Docker image with a scanner**](https://pythonspeed.com/articles/docker-secret-scanner/)  
    It’s easy to mistakenly embed a secret in your Docker image. Use a scanner to find these secrets before you leak them out potential attackers.
    
9. [**Security scanners for Python and Docker: from code to dependencies**](https://pythonspeed.com/articles/docker-python-security-scan/)  
    How do you know your Python code is secure? How about your Docker image? Learn how to catch problems is using security scanners running in your CI setup.
    
10. [**The security scanner that cried wolf**](https://pythonspeed.com/articles/docker-security-scanner/)  
    If you’ve ever been alarmed by how many security vulnerabilities your Docker image has, even after you’ve installed security updates, here’s what’s going on.
    

### [](https://pythonspeed.com/docker/#fast-builds-small-images)Fast builds, small images

1. [**The high cost of slow Docker builds**](https://pythonspeed.com/articles/high-cost-slow-docker-builds/)  
    A slow Docker build on the critical path for developer feedback is a lot more expensive than you think.
    
2. [**Elegantly activating a virtualenv in a Dockerfile**](https://pythonspeed.com/articles/activate-virtualenv-dockerfile/)  
    How to activate a Python virtualenv in a Dockerfile without repeating yourself—plus, you’ll learn what activating a virtualenv actually does.
    
3. [**Faster Docker builds with pipenv, poetry, or pip-tools**](https://pythonspeed.com/articles/pipenv-docker/)  
    Installing Python dependencies separately from your code speed ups Docker builds. Here’s how to do it with pipenv, poetry, or pip-tools.
    
4. [**Poetry vs. Docker caching: Fight!**](https://pythonspeed.com/articles/poetry-vs-docker-caching/)  
    Poetry’s versioning scheme for Python dependencies makes Docker caching harder, which means slower images rebuilds. Learn some workarounds.
    
5. [**Speed up pip downloads in Docker with BuildKit’s new caching**](https://pythonspeed.com/articles/docker-cache-pip-downloads/)  
    Every time you change your Python pip requirements and rebuild your Docker image, you’re going to redownload all your packages. You can fix this with BuildKit.
    
6. [**Speeding up Docker builds in CI with BuildKit**](https://pythonspeed.com/articles/speeding-up-docker-ci/)  
    If your CI runners spin up an empty environment, your Docker builds will be slow. Speed up builds by warming the cache, plus BuildKit’s extra speedup.
    
7. [**Making pip installs a little less slow**](https://pythonspeed.com/articles/faster-pip-installs/)  
    Installing packages with pip, Poetry, and Pipenv can be slow. Learn how to ensure it’s not even slower, and a potential speed-up.
    
8. [**Shrinking your Python application’s Docker image: an overview**](https://pythonspeed.com/articles/smaller-docker-images/)  
    Learn the variety of techniques you can use to make your Python application’s Docker image a whole lot smaller.
    
9. [**Multi-stage builds #1: Smaller images for compiled code**](https://pythonspeed.com/articles/smaller-python-docker-images/)  
    Building Docker images with compiled code can lead to huge images. Learn how to shrink them with multi-stage builds.
    
10. [**Multi-stage builds #2: Python specifics**](https://pythonspeed.com/articles/multi-stage-docker-python/)  
    Once you understand generic Docker multi-stage builds, here’s how to implement them for Python applications, with virtualenvs or user installs.
    
11. [**Multi-stage builds #3: Speeding up your builds**](https://pythonspeed.com/articles/faster-multi-stage-builds/)  
    Multi-stage Docker image builds give you small images and fast builds, but only if takes extra steps prevent slowness due to caching problems.
    

### [](https://pythonspeed.com/docker/#conda)Conda

1. [**Pip vs Conda: an in-depth comparison of Python’s two packaging systems**](https://pythonspeed.com/articles/conda-vs-pip/)  
    Python has two packaging systems, pip and Conda. Learn the differences between them so you can pick the right one for you.
    
2. [**Activating a Conda environment in your Dockerfile**](https://pythonspeed.com/articles/activate-conda-dockerfile/)  
    Learn how to activate a Conda environment in your Dockerfile.
    
3. [**Shrink your Conda Docker images with conda-pack**](https://pythonspeed.com/articles/conda-docker-image-size/)  
    Docker images built for Conda tend to be quite large. Learn how to shrink them by using the conda-pack tool and multi-stage builds.
    
4. [**Scanning your Conda environment for security vulnerabilities**](https://pythonspeed.com/articles/conda-security-scans/)  
    Learn how to check your Conda environment and packages for security vulnerabilities.
    
5. [**Reproducible and upgradable Conda environments with conda-lock**](https://pythonspeed.com/articles/conda-dependency-management/)  
    You want your packaging to be reproducible, and upgrade Conda dependencies without conflicts. Learn how to do it with a third-party tool: conda-lock.
    
6. [**Speed up your Conda installs with Mamba**](https://pythonspeed.com/articles/faster-conda-install/)  
    Conda installs are very slow, but you can speed them with a much-faster Conda reimplementation called Mamba.
    
7. [**Using Conda? You might not need Docker**](https://pythonspeed.com/articles/conda-vs-docker/)  
    Conda has some overlap with Docker’s functionality; sometimes you might not need Docker at all.
    

### [](https://pythonspeed.com/docker/#applications-and-runtime)Applications and runtime

1. [**Configuring Gunicorn for Docker**](https://pythonspeed.com/articles/gunicorn-in-docker/)  
    Running Gunicorn in a Docker container isn’t the same as running on a virtual machine or physical server. Learn what you need to do differently.
    
2. [**What’s running in production? Making your Docker images identifiable**](https://pythonspeed.com/articles/identifying-images/)  
    It’s difficult to debug production problems if you don’t know what image is running in production.
    
3. [**Decoupling database migrations from server startup: why and how**](https://pythonspeed.com/articles/schema-migrations-server-startup/)  
    Migrating your database schema when your application’s Docker container starts up? Here’s some reasons to rethink that choice.
    
4. [**A Python prompt into a running process: debugging with Manhole**](https://pythonspeed.com/articles/live-debugging-python/)  
    Your Python process is acting strange—learn how to get a live Python interpreter prompt inside your running process for debugging.
    
5. [**Please stop writing shell scripts**](https://pythonspeed.com/articles/shell-scripts/)  
    It is quite difficult to write correct shell scripts; you’re much better off just using Python.
    
6. [**Why new Macs break your Docker build, and how to fix it**](https://pythonspeed.com/articles/docker-build-problems-mac/)  
    New Macs can break your Docker image build in unexpected ways; learn why, and how to fix it.
    

### [](https://pythonspeed.com/docker/#packaging-as-a-process)Packaging as a process

1. [**A thousand little details: developing software for ops**](https://pythonspeed.com/articles/developing-tools-for-ops/)  
    Software for ops suffers both from historical complexity and from problem space complexity. Some generic suggestions, with Docker packaging as an example.
    
2. [**Your Docker build needs a smoke test**](https://pythonspeed.com/articles/test-your-docker-build/)  
    If you don’t test your Docker image before you push it, you’ll waste time (and maybe break production).
    
3. [**“Let’s use Kubernetes!” Now you have 8 problems**](https://pythonspeed.com/articles/dont-need-kubernetes/)  
    For smaller teams, Kubernetes is usually the wrong solution: too complex, too complicated, and with too much work to keep it running.
    

### [](https://pythonspeed.com/docker/#docker-variants-and-alternatives)Docker variants and alternatives

1. [**Docker BuildKit: faster builds, new features, and now it’s stable**](https://pythonspeed.com/articles/docker-buildkit/)  
    BuildKit is Docker’s new system for building images. It’s faster, has previously missing security featuers, and it’s finally stable.
    
2. [**Options for Python packaging: Wheels, Conda, Docker, and more**](https://pythonspeed.com/articles/distributing-software/)  
    Learn and compare the many ways to package your Python server for distribution: wheels, PEX, RPM/DEB, Conda, executables, Docker.
    
3. [**Docker vs. Singularity for data processing: UIDs and filesystem access**](https://pythonspeed.com/articles/containers-filesystem-data-processing/)  
    Containers allow for reproducibility of data processing applications. Docker is the most popular option, but Singularity is also well-suited to this use case.
    
4. [**Using Podman with BuildKit, the better Docker image builder**](https://pythonspeed.com/articles/podman-buildkit/)  
    Podman is a Docker replacment, and BuildKit is a new builder for Docker images. Learn how to use BuildKit together with Podman.
    
5. [**Building Docker images on GitLab CI: Docker-in-Docker and Podman**](https://pythonspeed.com/articles/gitlab-build-docker-image/)  
    Building Docker images with Gitlab CI can be a little complicated. Learn how to do it with Docker-in-Docker, or the simpler option of using Podman.