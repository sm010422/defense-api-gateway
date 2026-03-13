# 🛡️ C4I 시스템 - Defense API Gateway

[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.5.11-brightgreen.svg?logo=springboot)](#)
[![Java](https://img.shields.io/badge/Java-21-orange.svg?logo=java)](#)
[![Spring Cloud Gateway](https://img.shields.io/badge/Spring%20Cloud-Gateway-blue.svg?logo=spring)](#)
[![JWT](https://img.shields.io/badge/Security-JWT-red.svg)](#)
[![K3s](https://img.shields.io/badge/K3s-Kubernetes-blue.svg?logo=kubernetes)](#)

## 📌 프로젝트 개요

실시간 전술 객체 추적 시스템(C4I)의 최전방에서 모든 외부 트래픽을 통제하는
API 게이트웨이 마이크로서비스입니다.

단일 진입점(Single Point of Contact) 기반의 접근 통제와 안정적인 트래픽 라우팅으로
내부 마이크로서비스를 외부 비정상 접근으로부터 보호합니다.

## 🏗 시스템 아키텍처
```
외부 요청
    ↓
Defense API Gateway (인증/라우팅) ← server3
    ↓
Target Tracking Service (비즈니스 로직) ← server2
    ↓
PostgreSQL (데이터 저장) ← server2
```

## ✨ 핵심 기능

### 1. 🚦 트래픽 라우팅 (Dynamic Routing)
- 외부 요청 URL을 분석해 K3s 클러스터 내부 서비스로 정확하게 전달
- 내부 서비스의 실제 IP/포트를 외부에 노출하지 않음

### 2. 🔐 공통 인증/인가 필터 (JWT Auth Filter)
- JWT 기반 글로벌 보안 필터로 비인가 접근을 게이트웨이 단에서 차단
- 내부 서비스가 인증 로직 없이 비즈니스 로직에만 집중할 수 있는 구조

### 3. ⚖️ 로드밸런싱 (Load Balancing)
- K3s 내부 서비스 디스커버리와 연동
- 다중 Pod에 트래픽 분산

## 🛠 기술 스택

| 분류 | 기술 |
|------|------|
| Language | Java 21 |
| Framework | Spring Boot 3.5.11, Spring Cloud Gateway |
| Security | JWT, Spring Security |
| Infra | K3s (Kubernetes), Docker |

## 📋 구현 현황

- [x] 프로젝트 초기 세팅
- [x] Spring Cloud Gateway 의존성 구성
- [ ] JWT 인증 필터 구현
- [ ] Target Tracking Service 라우팅 설정
- [ ] K3s 클러스터 연동
- [ ] 로드밸런싱 설정

## 🔗 연관 리포지토리

- 🏗️ **[K3s MSA Infrastructure](https://github.com/sm010422/k3s-msa-infrastructure)** - 클러스터 인프라 구성
- 🎯 **[Target Tracking Service](https://github.com/sm010422/target-tracking-service)** - 핵심 비즈니스 로직
