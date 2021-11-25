# examples
audiolib AGC 기능 실행예제
<br/>
<br/>

# Features
Standard 버전에서는 AGC (Automaic Gain Control)기능을 제공합니다.
Audio PCM buffer interface가 제공되는 환경이면 본 프로젝트를 통해 AGC를 Intel x86/x64, ARM64, ARM32기반 등 다양한 플랫폼에 적용 가능합니다.

AGC는 Mic와 화자 간 거리에 따라 자동으로 송신음량을 최적화하는 기능입니다.

![AGC_IN_OUT](https://user-images.githubusercontent.com/75764437/142515569-30c9f4c5-b1ca-4668-93c7-e43e07bab56c.png)

마이크와 화자간의 거리가 멀어지면 음성신호의 크기가 줄어들어서 상대편에 작게 전달될 수가 있습니다.
AGC 기술을 통해 자동으로 적절한 음량으로 gain을 증가또는 감소시켜 전달 가능합니다. 이는 반대의 상황(마이크와 화자의 거리가 가까워져서 소리가 커지는 경우)에도 마찬가지로 적용됩니다.
<br/>
<br/>

# System Requirements
본 예제를 실행하기 위해 다음과 같은 환경이 필요합니다.
<br/>
OS: x86/x64용 Linux 계열, macOS, Windows (Cygwin또는 minGW 설치 필요)
<br/>
컴파일러: GCC 5.X 이상
<br/>
<br/>

# 라이브러리 실행 예제

<br/>

### AGC 프로세싱

#### 1. 설치

Clone 또는 내려받기를 통해 프로젝트 파일을 내려받습니다.
빌드에는 다음 파일들이 필요합니다.
<br/>
```
audiolib_example.c
vine_audio.h
vine_audio.c
agc/VineAGC.h
agc/libVineAGC.a
```

<br/>

#### 2. 시스템 command line에서 gcc로 다음과 같이 빌드합니다.
    
```
$ gcc -o audiolib_test testmain.c -Lagc -lVineAGC -std=c99 -lm
```


빌드에 성공하면 audiolib_test.exe 파일이 생성됩니다.
<br/>
PCM 샘플 파일을 실행파일이 있는 경로에 준비합니다. (PCM raw data format)
<br/>

* File Name: sample.pcm
* Sampling Rate: 8000Hz
<br/>
<br/>

#### 3. 빌드된 실행파일을 다음과 같이 실행합니다.

```
$ ./audiolib_test sample.pcm
```

AGC 프로세싱이 완료된 PCM파일이 생성됩니다.
```
sample_out.pcm
```
   
<br/>
<br/>

# License

[![License: LGPL v2.1](https://img.shields.io/badge/License-LGPL_v2.1-blue.svg)](https://www.gnu.org/licenses/lgpl-2.1)

<br/>
<br/>

# Copyright
Copyright (c) 2021, THE VINE CORPORATION All right reserved.
