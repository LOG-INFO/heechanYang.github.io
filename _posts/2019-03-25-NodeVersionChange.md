---
layout: post
title:  "NVM을 이용한 Node 버전 변경 - LOG.INFO"
date:   2019-03-25 16:14:27 +0830
categories: Nodejs
---

# 배경

이번에 `Node.js`를 배울 기회가 생겨 `node`의 버전을 변경하던 중 `NVM`이란 것을 알게 되어 이것을 이용하여 쉽게 `node`의 버전을 관리하는 방법을 공유한다.

# Node 버전 변경

## 1. Node 버전 확인

1. `win` + `r` 을 눌러 실행창을 켠 후, `cmd`를 입력하여 콘솔창을 켠다.
2. `node -v`를 입력하여 `node`의 버전을 확인한다.
   1. 참고로 2019년 03월 25일 기준으로 `node`의 최신 LTS(Long Term Support) 버전은 `10.15.3`이다.

## 2. NVM 설치

1. [`NVM-Windows`의 Github Repository](https://github.com/coreybutler/nvm-windows/)로 가서 `NVM` 설치파일을 [다운로드](https://github.com/coreybutler/nvm-windows/releases) 받는다.
2. 필자의 경우 `nvm-setup.zip`를 다운받아 압축을 푼 후 설치하였는데, `nvm-noinstall.zip`를 다운 받은 후 `nvm.exe`를 바로 실행해도 될 듯.(이건 안 해봄)

## 3. Node 버전 변경

1. 다시 `win` + `r` 을 눌러 실행창을 켠 후, `cmd`를 입력하여 콘솔창을 켠다.
2. `nvm list available`를 입력하면 사용 가능한 `Node` 버전들이 조회된다.
3. `nvm install {원하는 버전}`을 입력하면 자동으로 해당 버전의 `Node`를 다운로드하여 설치 한다.
4. `nvm list`를 입력하면 컴퓨터에 설치되어 사용 가능한 `Node`의 버전들이 조회된다.
5. `nvm use {원하는 버전}`을 하면 해당 버전으로 변경된다.
6. 끄읕~내기 전에 `node -v`를 통해 제대로 변경되었는지 확인하자.

# 참고문헌

- [NVM 으로 NODE버전 컨트롤 하기](https://krauser085.github.io/node.js-01-use-nvm/)
- [nvm-windows Github Repository](https://github.com/coreybutler/nvm-windows)