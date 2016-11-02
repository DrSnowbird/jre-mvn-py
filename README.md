# Java 8 (1.8.0_112) JRE server + Maven 3.3.9 + Python 2.7.12

[![](https://imagelayers.io/badge/openkbs/jre-mvn-py:1.0.0.svg)](https://imagelayers.io/?images=openkbs/jre-mvn-py:1.0.0 'Get your own badge on imagelayers.io')

## Components:
* java version "1.8.0_112"
Java(TM) SE Runtime Environment (build 1.8.0_112-b15)
Java HotSpot(TM) 64-Bit Server VM (build 25.112-b15, mixed mode)
Java home: /usr/jdk1.8.0_112/jre
* Apache Maven 3.3.9 (bb52d8502b132ec0a5a3f4c09453c07478323dc5; 2015-11-10T16:41:47+00:00)
* Python 2.7.12
* Other tools: git wget unzip vim python python-setuptools python-dev python-numpy 

## Pull the image from Docker Repository

```bash
docker pull openkbs/jre-mvn-py
```

## Base the image to build add-on components

```Dockerfile
FROM openkbs/jre-mvn-py
```

## Run the image

Then, you're ready to run :
Make sure you create your work directory, e.g., /data

```bash
mkdir ./data
docker run -d --name my-jre-mvn-py -v $PWD/data:/data -i -t openkbs/jre-mvn-py
```

## Build and Run your own image

Say, you will build the image "my/jre-mvn-py".

```bash
docker build -t my/jre-mvn-py .
```

To run your own image, say, with some-jre-mvn-py:

```bash
mkdir ./data
docker run -d --name some-jre-mvn-py -v $PWD/data:/data -i -t my/jre-mvn-py
```

## Shell into the Docker instance
```bash
docker exec -it some-jre-mvn-py /bin/bash
```

## Run Python code
To run Python code 

```bash
docker run --rm openkbs/jre-mvn-py python -c 'print("Hello World")'
```

or,

```bash
mkdir ./data
echo "print('Hello World')" > ./data/myPyScript.py
docker run -it --rm --name some-jre-mvn-py -v "$PWD"/data:/data openkbs/jre-mvn-py python myPyScript.py
```

or,

```bash
alias dpy='docker run --rm openkbs/jre-mvn-py python'
dpy -c 'print("Hello World")'
```

