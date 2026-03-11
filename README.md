# 🛡️ C4I 시스템 - Defense API Gateway

[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen.svg?logo=springboot)](#) [![Spring Cloud Gateway](https://img.shields.io/badge/Spring%20Cloud-Gateway-blue.svg?logo=spring)](#) [![Java](https://img.shields.io/badge/Java-17-orange.svg?logo=java)](#)

## 📌 프로젝트 개요
실시간 전술 객체 추적 시스템(MSA)의 최전방에서 모든 외부 트래픽을 통제하고 보호하는 API 게이트웨이(수문장) 서비스입니다.

국방/방산 시스템의 핵심인 '단일 진입점(Single Point of Contact) 기반의 철저한 접근 통제'와 '안정적인 트래픽 라우팅'을 구현하여 내부 마이크로서비스들을 외부의 비정상적인 접근으로부터 안전하게 보호합니다.

## ✨ 핵심 기능 (Key Features)

### 1. 🚦 지능형 트래픽 라우팅 (Dynamic Routing)
* 외부 클라이언트의 요청 URL을 분석하여, K3s 클러스터 내부망에 숨겨져 있는 알맞은 비즈니스 서비스(예: `target-tracking-service`)로 트래픽을 정확하게 전달합니다.
* 내부 서비스의 실제 IP와 포트를 외부로 절대 노출하지 않는 완벽한 은닉화를 제공합니다.

### 2. 🔐 공통 인증/인가 필터 (Security & Auth Filter)
* **JWT(JSON Web Token)** 기반의 글로벌 보안 필터를 적용하여, 인가되지 않은 사용자(또는 비정상 기기)의 접근을 게이트웨이 단에서 원천 차단합니다.
* 내부 서비스들이 각각 인증을 처리할 필요 없이, 오직 핵심 비즈니스 로직에만 집중할 수 있도록 아키텍처를 최적화했습니다.

### 3. ⚖️ 로드밸런싱 (Load Balancing)
* 쿠버네티스(K3s)의 내부 서비스 디스커버리와 연동하여, 다중 복제된 파드(Pod)들에게 트래픽을 골고루 분산시킵니다.

## 🛠 기술 스택 (Tech Stack)
* **Framework:** Java 17, Spring Boot 3.x, Spring Cloud Gateway
* **Security:** JWT, Spring Security
* **Infra:** K3s (Kubernetes), Docker

## 🔗 연관 리포지토리
* 🏗️ **[K3s MSA Infrastructure (인프라 구성도)](https://github.com/sm010422/k3s-msa-infrastructure)**
* 🎯 **[Target Tracking Service (핵심 처리 로직)](https://github.com/sm010422/target-tracking-service)**
