# 강의 목표
- 제대로 만드는 애플리케이션
- 보안이 왜 필요한지
- 보안에 정석은 없음
    - 내 상황에 맞는 개발/운영/보안 시나리오 수립
- 네트워크 보안
- 로그 확인 방법


# 웹보안
- 취약점 점검 도구
- TLS 보안 --> HTTPS

## 법률
- 개인정보 플레인 텍스트 X
- 네트워크 방화벽
- 패스워드 단방향 해시

# 개발자가 알아야 할 보안

# 해킹방법
- 피싱 (Phishing), 스피어 피싱 (Spear-Phishing)
- 바이러스 : + 실행파일 O
- 웜 
    - 스스로 복제하는 컴퓨터 프로그램
    - 바이러스와 유사하지만 독자적으로 실행
    - ex) 
        - Slammer Worm : 30분 만에 전세계로 퍼짐, 10년 후에도 여전히 활동 중
- 루트킷/트로이목마/백동 : 루트권한
- 랜섬웨어 : 데이터 탈취하여 금전적 이득을 챙김


# 보안 용어

## CVE(Common Vulnerabilities and Exposure)
- http://cve.mitre.org
- 공개적으로 알려진 소프트웨어 보안 취약점을 가리키는 고유 표기법

## 전산망 사이버테러

## APT 공격
: 특정 타겟에 대한 지능적이고 지속적인 위협
- Advanced(지능적)
- Persistent(지속적)
- Threat(위협)
<br>
<br>
# 보안의 3요소 (CIA)
## 보안 이론
- Confidentiality(기밀성)
    - 정의
        - 비밀 유지
        - 인가된 사용자만 접근 가능
    - 방법
        - 암호화
        - 인증
    - 위협
        - 도청(Sniffing)
        - 사회공학(SOcial Engineering)
- Integrity(무결성) (데이터 변조를 탐지)
    - 정의
    - 방법
        - 물리적 통제, 접근 통제
        - 무결성 검증 (Hash - MD5, SHA-1)
        - 해시확인툴 - MD5sum, sha256
    - 
- Availability(가용성)

## 보안 체계
- 물리적 보안
    - CCTV, 지문감식기, ...
- 기술적 보안
    - OPT, VPN, V3, ...
- 관리적 보안
    - 예방 및 대응 방법 수립

# 네트워크 보안
## 네트워크 통신 기본 이론
### OSI 7 Layer
### 방화벽 정책
- AWS Security Group
- 

## 패킷 덤프 실습 (wireshark)

# AWS 서버 보안 아키텍처
## AWS 서버 구축 기본 (VPC, SG)
- 사용자 보안 : IAM
- 네트워크 보안 : VPC
- 서버 보안 : SG, EC2(linux)
- 서비스 보안 : (nginx)
- 가용성: ELB, AutoScaling

Root계정 multi-factor 인증\
Root계정은 IAM 계정을 생성할 때만 사용하고 그 외엔 절대 사용하지 않는다\
서버마다 IAM 유저 할당\
서브 계정을 만들어서 사용하고\
제한적으로(package 설치 등) sudo 를 통해 root 계정의 권한을 빌려와서 사용

## 3-tier Architecture
public subnet(Web server) - private subnet(DB, WAS)

# 웹 해킹 기법
## 구글 해킹 
- 검색어 : 주민등록번호 filetype:xls
## Burpsuite를 이용한 패킷 캡쳐/변조

## 진단도구
- OWASP ZAP
    - 나중에 이거 사용해서 보안 진단했다고 하면 가점 있을거임~ 

## 웹 해킹 실습
- SQL injection
- XSS
- Directory Listing 옵션 등

# 그냥 팁
## lastb

## AWS가 해킹 안 당하는 이유?
- 비대칭키 로그인방식 덕분!
- 팀 프로젝트에선 키를 옮겨야하지 않나?
- 사용자 계정을 만들어라

## http://map.norsecorp.com/

