🌐 본사–지부 통합 무선 네트워크 보안 설계
<p align="center"> <img src="https://img.shields.io/badge/Wireless-WPA2%20Personal%20%26%20Enterprise-blue?style=flat-square"/> <img src="https://img.shields.io/badge/Routing-OSPF-green?style=flat-square"/> <img src="https://img.shields.io/badge/Simulator-PacketTracer-orange?style=flat-square"/> <img src="https://img.shields.io/badge/Author-Jo%20Hyunho-9cf?style=flat-square"/> </p>
📘 개요

본 프로젝트는 본사 – 서울지부 – 수원지부로 구성된 기업 네트워크 환경을 기반으로
무선 보안 통신, AAA 인증, 라우팅(OSPF), DNS 구성 등을 Packet Tracer에서 구현한 설계 문서입니다.

구성 목표:

WPA2-Personal / WPA2-Enterprise 무선 AP 구성

AAA(RADIUS) 기반 인증

DHCP 기반 자동 IP 할당

OSPF 라우팅

DNS 서버 분산

전체 통신 테스트 성공

📡 무선 AP 구성
🔹 AP1 (WPA2-Personal)

| 항목         | 설정값                    |
| ---------- | ---------------------- |
| 외부 IP      | DHCP (192.168.0.12/24) |
| 내부망        | 192.168.100.1/24       |
| SSID       | Slave032               |
| Security   | WPA2-Personal          |
| Encryption | AES                    |
| Passphrase | 과제 제출 시 기재             |

🔹 AP2 (WPA2-Enterprise)
| 항목             | 설정값              |
| -------------- | ---------------- |
| 외부 IP          | 192.168.40.1/24  |
| 내부망            | 192.168.201.1/24 |
| Security       | WPA2-Enterprise  |
| Authentication | AAA/RADIUS       |
| Encryption     | AES              |


🖥 AAA · RADIUS 서버

본사 서버는 AAA(RADIUS)를 이용해 AP2의 인증을 수행합니다.

사용자 인증(Authentication)

권한 부여(Authorization)

접속 기록(Accounting)

WPA2-Enterprise 인증 처리

🌐 DNS 구성
구역	DNS 서버 IP
본사	32.1.0.5
서울지부	32.1.0.6
수원지부	32.1.0.7
🧭 라우팅 (OSPF)

전 구간에서 OSPF 라우팅 프로토콜 사용.

선택 이유:

RIP는 Subnet/VLSM 미지원 → 지부 네트워크에 비효율적

OSPF는 규모 확장성·안정성 우수

네트워크 확장 시 자동 재계산

🧪 테스트 결과

✔ PC → 본사 서버 Ping 정상

✔ WPA2-Personal 연결 정상

✔ WPA2-Enterprise 인증 정상

✔ 본사–서울–수원 모든 구간 통신 정상

✔ DNS 응답 정상

📁 포함 파일
프로젝트 폴더/
 ├─ README.md        # 이 문서
 ├─ report.docx      # 기말 보고서 파일
 ├─ project.pkt      # Packet Tracer 파일
 └─ images/ (선택)

📌 결론

본 네트워크 설계는 다음을 충족합니다:

기업 환경에 적합한 무선 보안 구조

WPA2 Personal + Enterprise 혼합 운영

AAA(RADIUS) 인증 기반

OSPF 기반 안정적 라우팅

Packet Tracer에서 전체 시뮬레이션 검증

보안성, 확장성, 유지보수성을 모두 고려한 완성도 높은 설계입니다.
