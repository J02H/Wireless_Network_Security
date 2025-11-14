🌐 본사–지부 통합 무선 네트워크 보안 설계
<p align="center"> <img src="https://img.shields.io/badge/Wireless-WPA2%20Personal%20%26%20Enterprise-blue?style=flat-square"/> <img src="https://img.shields.io/badge/Routing-OSPF-green?style=flat-square"/> <img src="https://img.shields.io/badge/Simulator-PacketTracer-orange?style=flat-square"/> <img src="https://img.shields.io/badge/Author-Jo%20Hyunho-9cf?style=flat-square"/> </p>
📘 프로젝트 개요

본 문서는 본사–서울 지부–수원 지부로 구성된 기업 네트워크 환경에서
무선 보안 인프라 및 라우팅 구조를 설계·구현한 내용을 정리한 문서입니다.

구현 목표:

본사 AAA 서버 기반 인증 구조

WPA2-Personal / WPA2-Enterprise 무선 AP 구성

DHCP 기반 자동 IP 할당

OSPF 기반 라우팅

분산 DNS 서버 구성

Packet Tracer 환경에서 모든 네트워크 통신 검증

📡 무선 AP 구성
🔹 AP1 (WPA2-Personal)
항목	값
외부 IP	DHCP (192.168.0.12/24)
내부망	192.168.100.1/24
SSID	Slave032
Security	WPA2-Personal
Encryption	AES
Passphrase	(과제 제출 시 기재됨)
🔹 AP2 (WPA2-Enterprise)
항목	값
외부 IP	192.168.40.1/24
내부망	192.168.201.1/24
Security	WPA2-Enterprise
Authentication	AAA/RADIUS 서버
Encryption	AES
🖥 AAA/RADIUS 서버 구성

본사 서버는 AAA + RADIUS 역할 수행:

사용자 인증(Authentication)

권한 부여(Authorization)

접속 기록(Accounting)

AP2의 WPA2-Enterprise 인증 처리

🌐 DNS 구성
구역	IP
본사 DNS	32.1.0.5
서울지부 DNS	32.1.0.6
수원지부 DNS	32.1.0.7
🧭 라우팅 구성 (OSPF)

본 네트워크는 RIP의 한계(서브넷/VLSM 미지원)를 피하기 위해
전 구간 OSPF 라우팅 프로토콜을 사용했습니다.

서브넷 분할 지원

대규모 트래픽 환경에서도 빠른 수렴

확장성 우수

지부 추가 시 구조적 변화 없이 적용 가능

🧪 테스트 결과

✔ PC → 본사 서버 Ping 정상

✔ WPA2-Personal 연결 정상

✔ WPA2-Enterprise 인증 정상

✔ 본사–서울–수원 구간 전부 통신 정상

✔ DNS 응답 정상

📁 포함 파일
📁 프로젝트 폴더
 ├── README.md
 ├── report.docx          # Word 과제 파일
 ├── project.pkt          # Packet Tracer 파일
 └── images/ (선택)

📌 결론

기업 환경을 고려한 무선 보안 네트워크 구현

WPA2 Personal + Enterprise 혼합 구성

AAA 기반 인증 인프라 설계

OSPF 기반 안정적 라우팅

Packet Tracer로 전체 설계 검증 완료

보안성·확장성·유지보수성을 모두 고려한 네트워크 설계를 완성했습니다.
