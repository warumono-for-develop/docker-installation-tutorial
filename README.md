<!-- SHIELDS -->



[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]



<!-- LOGO -->



<br />
<p align="center">
  <a href="https://github.com/warumono-for-develop/docker-installation-tutorial">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h1 align="center">Docker Installation Tutorial</h1>

  <p align="center">
    AWS EC2 인스턴스에 Docker 프로그램 설치 관련 지침서
    <br />
    <a href="https://github.com/warumono-for-develop/docker-installation-tutorial"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/warumono-for-develop/docker-installation-tutorial">View Tutorial</a>
    ·
    <a href="https://github.com/warumono-for-develop/docker-installation-tutorial/issues">Report Bug</a>
    ·
    <a href="https://github.com/warumono-for-develop/docker-installation-tutorial/issues">Request Feature</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->



## Table of Contents

* [About the Tutorial](#about-the-tutorial)
  * [Official Website](#official-website)
  * [Built With](#built-with)
* [Getting Started](#getting-started)
  * [References](#references)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
    * [Step 1 python3-pip 프로그램 설치](#step-1)
    * [Step 2 Jupyter Notebook 설치](#step-2)
    * [Step 3 Jupyter Notebook 비밀번호 설정](#step-3)
    * [Step 4 Jupyter Notebook 설정 파일 생성 및 편집](#step-4)
    * [Step 6 Jupyter Notebook 백그라운드 실행 설정](#step-5)
* [Usage](#usage)
  * [Run Jupyter Notebook](#run-jupyter-notebook)
  * [Connect to Jupyter Notebook](#connect-to-jupyter-notebook)
  * [Jupyter Notebook Dashboard](#jupyter-notebook-dashboard)
* [Roadmap](#roadmap)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)
* [Acknowledgements](#acknowledgements)



<!-- ABOUT THE PROJECT -->



## About The Tutorial

AWS EC2 인스턴스에 새로운 환경 설정을 하기에 편리하며

가벼운 프로세스 연동으로 서버 전반적으로 가벼운 구동이 가능

Docker 를 사용하는 이유 :
* 가벼운 프로세스 구동
* 환경 설정 용이

*Docker 외 다른 프로그램 또는 그 외 방법들도 있겠지만, Docker 프로그램을 써보는 것도 추천*

### Official Website

공식 사이트 또는 관련 정보를 미리 숙지하고 사용할 것을 권장

* [Docker](https://www.docker.com/)

### Built with

#### Required

- [x] [Docker](https://www.docker.com/)

  Docker version 19.03.6

- [x] [AWS](https://aws.amazon.com/ko/) EC2 Instance

  \[Free tier\] Ubuntu Server 18.04 LTS (HVM), SSD Volume Type

#### Optional

- [ ] [Jupyter Notebook](https://jupyter.org/)

  [Jupyter Notebook Installation Tutorial](https://github.com/warumono-for-develop/jupyter-notebook-installation-tutorial)



<!-- GETTING STARTED -->



## Getting Started

Docker 설치는 터미널을 이용하여 명령어를 입력하는 작업이 많으므로 진행 순서와 오탈자에 주의

*본 작업을 진행에 앞서 프로그램을 설치할 대상 서버는 반드시 백업 완료 후 진행할 것을 권장*

*사용자가 사용하는 프로그램 버전과 환경 등에 따라 설명글의 진행 절차와 결과가 다소 다르거나 생략 또는 추가 작업이 있을 수 있음*

*설명글에 사용되는 용어 및 단어 등은 되도록 공식적(?)으로 사용되는 것으로 표기하였으나 오탈자 및 잘못된 용어 또는 정보가 있을 수 있음*

### References

**_`your-teminal>`_** 사용자의 터미널 프로그램 프롬프트를 나타내며 입력하는 문자가 아님

**_`{your-xxx}`_** 사용자가 정의해야하는 항목 변수이며 사용자가 직접 임의의 이름이나 특정된 값 등으로 입력

**_`{auto-xxx}`_** 사용자의 요청에 따른 결과 항목 변수이며 프로그램이 임의의 이름이나 특정된 값 등으로 노출

### Prerequisites

#### AWS EC2 인스턴스 **생성** 및 **활성화**

기존 AWS EC2 인스턴스 또는 새로운 인스턴스를 생성하여 정상적으로 구동중인 서버

### Installation

#### Step 1

##### Plugin 설치

```sh
your-terminal> sudo apt update

your-terminal> sudo apt install apt-transport-https

your-terminal> sudo install ca-certificates

your-terminal> sudo install curl

your-terminal> sudo install software-properties-common

your-terminal> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

your-terminal> sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"

your-terminal> sudo apt update
```

#### Step 2

##### Docker 설치

```sh
your-terminal> apt-cache policy docker-ce

your-terminal> sudo apt install docker-ce
```

#### Step 3

##### Docker 상태 확인

*상태 확인 후, **_`control + C`_** 키를 눌러 Docker 에서 나옴*
    
```sh
your-terminal> sudo systemctrl status docker
```



<!-- USAGE EXAMPLES -->



## Usage

정상적으로 Docker 설치 및 설정이 완료되었다면 실행하여 Sample 구동

Docker 공식 사이트에서 제공하는 샘플(?) image `hello-world` 를 다운로드하여 구동하는 것으로 Docker 기본 사용방법을 연습

Docker 명령어는 공식 사이트 또는 인터넷 등으로 미리 숙지하고 사용하는 것을 권장

다음 명령어와 같이 모든 명령어의 뒤에 `--help` 를 입력하면 해당 명령어의 사용법이 표기 됨

```sh
your-terminal> docker xxxx --help
```

#### Pull image

Docker Hub 에 등록되어 공개되어 있는 image 를 검색하는 명령어

docker **search** `{your-docker-image-name-search-keyword}`

Docker Hub 로 부터 해당 image 를 로컬 저장소로 다운로드 하는 명령어

docker **pull** `{your-docker-image-name}`

```sh
your-terminal> docker pull hello-world
```

#### List images in local Docker

docker images

```sh
your-terminal> docker images

REPOSITORY                     TAG                 IMAGE ID            CREATED             SIZE
hello-world                    latest              fce289e99eb9        14 months ago       1.84kB
```

#### Run container

docker **run** `{your-docker-image-name}`

```sh
your-terminal> docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

`hello-world` 프로그램은 구동된 후에 서버가 임의의 작동을 완료되면 프로그램을 종료하는 방식이 아닌, **사용자가 중지시키기전까지 연속적으로 구동되고 있어야 하는 프로그램**(API 서버 등)은 옵션 명령어 `-d` 를 사용

```sh
your-terminal> docker run -d -p 9090:8080 `{your-docker-image-name}`
```

#### List containers in Docker

docker **ps -a**

```
your-terminal> docker ps -a

CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                     PORTS                         NAMES
d3d5ae2842b1        hello-world         "/hello"                 3 minutes ago       Exited (0) 3 minutes ago                         sad_haibt
```

#### Stop container

docker **stop** `{your-docker-container-id}`

```
your-terminal> docker stop hello-world

CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                     PORTS                         NAMES
d3d5ae2842b1        hello-world         "/hello"                 3 minutes ago       Exited (0) 3 minutes ago                         sad_haibt
```

#### Stop container

docker **stop** `{your-docker-container-id}`

```
your-terminal> docker stop hello-world

CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                     PORTS                         NAMES
d3d5ae2842b1        hello-world         "/hello"                 3 minutes ago       Exited (0) 3 minutes ago                         sad_haibt
```



<!-- ROADMAP -->



## Roadmap

See the [open issues](https://github.com/warumono-for-develop/docker-installation-tutorial/issues) for a list of proposed features (and known issues).



<!-- CONTRIBUTING -->



## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project

2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)

3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)

4. Push to the Branch (`git push origin feature/AmazingFeature`)

5. Open a Pull Request



<!-- LICENSE -->



## License

Distributed under the MIT License. See [`LICENSE`][license-url] for more information.



<!-- CONTACT -->



## Contact

**warumono** - warumono.for.develop@gmail.com

Project link: [https://github.com/warumono-for-develop/docker-installation-tutorial](https://github.com/warumono-for-develop/docker-installation-tutorial)



<!-- ACKNOWLEDGEMENTS -->



## Acknowledgements

* [안경잡이개발자](https://ndb796.tistory.com/)



<!-- MARKDOWN LINKS & IMAGES -->



<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/warumono-for-develop/docker-installation-tutorial.svg?style=flat-square
[contributors-url]: https://github.com/warumono-for-develop/docker-installation-tutorial/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/warumono-for-develop/docker-installation-tutorial.svg?style=flat-square
[forks-url]: https://github.com/warumono-for-develop/docker-installation-tutorial/network/members
[stars-shield]: https://img.shields.io/github/stars/warumono-for-develop/docker-installation-tutorial.svg?style=flat-square
[stars-url]: https://github.com/warumono-for-develop/docker-installation-tutorial/stargazers
[issues-shield]: https://img.shields.io/github/issues/warumono-for-develop/docker-installation-tutorial.svg?style=flat-square
[issues-url]: https://github.com/warumono-for-develop/docker-installation-tutorial/issues
[license-shield]: https://img.shields.io/github/license/warumono-for-develop/docker-installation-tutorial.svg?style=flat-square
[license-url]: https://github.com/warumono-for-develop/docker-installation-tutorial/blob/master/LICENSE
[product-screenshot]: images/screenshot.png
