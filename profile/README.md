<div align="center">
<h2>멀티 클라우드 스팟 인스턴스 통합 관리 플랫폼, "Keep Your Cost"</h2>
<img alt="image" width="100%" src="https://github.com/KeepYourCost/.github/blob/main/assets/kyc-logo.png?raw=true"/>


</div>

## 🫴🏻 Project Introduction
### Background & Purpose
SW 분야 종사자들이 CSP를 사용하면서 가장 우선으로 고려하는 부분은 **`비용`** 입니다.
  
AWS를 기준으로, VM을 사용함에 스팟 인스턴스는 일반 인스턴스 대비 **약 80% 저렴하게 사용할 수 있는 선택지**입니다.

하지만 여분의 자원을 경매 형식으로 제공하는 스팟 인스턴스의 특성상 <span style="color:red;"><strong>긴급 종료 위험</strong></span>과 <span style="color:red;"><strong>데이터 이전 작업의 반복</strong></span>이 문제로 지적되고 있습니다.

이런 스팟 인스턴스의 위험에 가장 많이 노출된 부분은 AI 모델 학습 도메인입니다.

AI 모델 학습에서 클라우드 환경은 많이 채택되는 선택지입니다. GPU 자원 비용을 줄이기 위해 사용자들은 많은 고민을 하고 있고, 이에 스팟 인스턴스는 좋은 선택지가 될 수 있습니다.  

그러나 긴급 종료 위험과 데이터 이전 작업의 반복이란 두 개의 큰 위험 때문에 쉽게 도입하지 못하는 상황입니다.
 
본 프로젝트는 인스턴스의 동적 생성과 데이터 스트리밍을 통한 파이프라인 구축을 자동화함으로써 **멀티 클라우드 환경에서 단일 인터페이스로 비용 절감 효과를 극대화할 수 있는 오픈 소스 플랫폼 구축을 목표**로 합니다.

### We Expect...
이 오픈소스 프로젝트는 특정 AWS 리전 제약 없이 최적의 비용의 스팟 인스턴스를 검색하고 자동으로 생성하며, Kafka를 이용해 데이터 손실 없이 스트리밍을 통해 이전 작업을 자동화합니다.

이를 통해 스팟 인스턴스의 불안정성을 해결하고 멀티 클라우드 환경에서 스팟 경매를 단일 인터페이스로 통합하여 관리할 수 있는 자동화된 시스템을 구축하였습니다. 

가장 스팟 인스턴스를 잘 활용할 수 있는 AI 모델 학습 분야에서 클라우드 고정 비용과 인프라 구축 비용이라는 AI 시장의 주요 걸림돌을 줄이고, AI 생태계의 발전을 촉진시켜 SW 시장의 전체적인 품질 향상에 기여할 수 있겠습니다.

AI 분야 뿐만 아니라, 다양한 데이터 처리 및 비용 효율적인 클라우드 인프라 운영이 필요한 모든 SW 분야에서 널리 활용될 수 있다 기대합니다.


## 👨‍👩‍👦 Moment Team 
<div align="center">

| FE | BE | BE | 
| :---: | :---: | :---: | 
| <img width="130px" src="https://avatars.githubusercontent.com/u/22852287?v=4" /> | <img width="130px" src="https://avatars.githubusercontent.com/u/76484900?v=4"/> |  <img width="130px" src="https://avatars.githubusercontent.com/u/102293576?v=4" /> |  
| 강은솔 | 반영환 | 김정래 |
|세종대학교|서울과학기술대학교|세종대학교|
|소프트웨어학과 4학년|ITM전공 4학년|컴퓨터공학 4학년|
|  [@eunsolkang](https://github.com/eunsolkang)  | [@lopahn2](https://github.com/lopahn2) |  [@Jeong-Rae](https://github.com/Jeong-Rae)   | 

</div>

## 📹 KYC 전체 시스템 사용 영상

[![Screenshot 2024-08-29 at 6 32 47 PM](https://github.com/user-attachments/assets/727867c3-e1cd-41f2-b75e-5c570aa1a706)](https://www.youtube.com/watch?v=ymfQopGpaKo)
  
## 1️⃣ **사용자 CSP Credential 등록**

### Key Enrollment
- [데모 버전 CSP] AWS
- 사용자가 사용할 Access Key와 Secret Key를 로컬 환경 플랫폼에 등록합니다.
  

![My Movie 3](https://github.com/user-attachments/assets/ac3771ed-b9cf-41f5-9fda-90c2a79ffb14)

## 2️⃣ **스팟 인스턴스 배포**

### Spot 스펙 작성 및 Terraform 기반 배포
- 사용자가 원하는 Region, Instance Spec, Instance Count ... 을 작성 후 배포 요청
- Event 창에서 Terraform을 통해 배포되는 Log 실시간 스트리밍으로 확인 가능

![My Movie 1](https://github.com/user-attachments/assets/74fb714c-cc7f-4743-8f83-04dc7ee4dd40)


## 3️⃣ **스팟 인스턴스 조회**

### 스팟 인스턴스 상태 확인
- KYC Dashboard에서 스팟 인스턴스들의 상태와 상세 스펙 확인 가능
![My Movie 1 (1)](https://github.com/user-attachments/assets/d57c9f01-f11d-4f07-b76f-ffbd5d231cb7)

## 4️⃣ **스팟 인스턴스 종료 이벤트 처리**
### 종료 이벤트 강제 발생
- 데모 버전에서, 랜덤하게 발생하는 Event를 시연할 수 없어 API Call을 통한 과정 데모
- 종료 이벤트 발생 시 새로운 스팟 인스턴스 배포

### 데이터 자동 백업
- 삭제 이벤트가 발생된 인스턴스에서 실행되는 Stream Agent로 기존 처리중이던 파일들을 Kafka 메시지 토픽에 프로듀싱
- 새로운 스팟 인스턴스가 배포되면, Stream Agent에서 자신의 Spot Instance Id를 통해 자신의 파일을 컨슈밍해 백업 진행
![My Movie 1 (3)](https://github.com/user-attachments/assets/081b8c29-2ac8-49c5-a2f1-9206d0abb304)


## 🔧 Tech Stack
### 🖥 User Interface
|🧑🏻‍💻  강은솔 | 📚 Tech Stacks  |
|:---:|:---:|
|Dev Packages |``React`` ``Redux`` ``Axios`` |
|Development Support Tools  |``ESLint`` ``Prettier``  ``Vercel`` ``Vite``|
#### ▶ How to install
- Master Agent와 함께 이미지로 배포됩니다. 

### 💻 Master Agent
|🧑🏻‍💻  반영환 | 📚 Tech Stacks  |
|:---:|:---:|
| Environment |``InteliJ`` ``Postman`` ``Git Action`` ``Git`` ``Gradle`` |
| Development  |``Spring-Boot v3.2.1`` ``Spring v6.1.2`` ``Java17`` ``Terraform v1.9.5``|
|Dependencies| ``Spring Security`` ``JWT(Json Web Token)`` ``Lombok`` ``Validation`` ``WebClient``|
|Deployment| ``Docker Image with User Interface`` |
#### ▶ How to install
이미지 배포되면, 테스트해보고 여기 작성해놓겠습니다.

### 💻 Stream Agent
|🧑🏻‍💻  김정래 | 📚 Tech Stacks  |
|:---:|:---:|
| Environment |``InteliJ`` ``Postman`` ``Git Action`` ``Git`` ``Gradle`` |
| Development  |``Spring-Boot v3.2.1`` ``Spring v6.1.2`` ``Java17`` ``Terraform v1.9.5``|
|Dependencies| ``Spring Security`` ``JWT(Json Web Token)`` ``Lombok`` ``Validation`` ``WebClient``|
|Deployment| ``Docker Image with User Interface`` |
#### ▶ How to install
- 기본적으로 배포되는 Spot Instance 내에서 자동 실행됩니다.
- [Install Guide](https://github.com/KeepYourCost/StreamAgent/blob/master/README.md)

### Additional Explain
시스템의 고가용성과 성능 향상을 목적으로 Stream Agent와 Master Agent의 분리 및 경량화된 서버를 구성을 위한 설계에 집중했습니다. 

1. Master Agent

- Master Agent는 사용자 인터페이스와 직접적으로 통신하는 시스템입니다. 사용자 경험을 극대화하고, 빠른 응답성을 제공하기 위해 Spring Boot 프레임워크를 사용하여 서버를 구성하였습니다. 

- Spring Boot는 강력한 기능과 유연성을 제공하며, 안정적이고 효율적인 서버 환경을 구축하는 데 기여합니다.

2. Stream Agent

- Stream Agent는 서버와의 통신을 수행하지만, 사용자 인터페이스와는 직접적인 연관이 없으며, 경량화된 설계를 통해 사용자 환경에 부담을 최소화하는 데 중점을 두었습니다. 

- 이를 위해 프레임워크를 사용하지 않고, 직접 구현한 HTTP API를 통해 통신을 수행하였습니다. 이러한 접근 방식은 Stream Agent의 성능을 향상하고, 시스템 자원 소모를 줄이는 데 기여합니다.

3. 파일 시스템 기반 데이터 저장

- 본 프로젝트는 오픈 소스 프로젝트로 배포되며, 사용자 환경에서의 실행 경량화를 고려하여 데이터 저장 방식에서도 최적화를 진행하였습니다. 데이터베이스 대신 파일 시스템을 사용하여 데이터 저장 및 관리를 수행함으로써, 시스템 부하를 줄이고 운영 효율성을 높이기 위한 노력을 기울였습니다.
 
- 파일 시스템 기반의 접근은 복잡성을 줄이고, 시스템 자원의 소모를 최소화하는 데 중요한 역할을 합니다.


## 🧾 KYC Architecture
### 🧾 System Architecture
<div align="center">

<img width="720" alt="KYC_System_Architecture" src="https://github.com/user-attachments/assets/8caad386-7ae8-4056-b6de-395856c3da69">
<img width="720" alt="KYC_Application_Architecture" src="https://github.com/user-attachments/assets/0ff66108-c600-47d6-bcdd-8204dc61dc27">

### 🧾 Fuction Architecture
<img width="720" alt="KYC_Sequence_Diagram_1" src="https://github.com/user-attachments/assets/0333175f-d81d-4915-9d48-43d75d29213b">
<img width="720" alt="KYC_Sequence_Diagram_2" src="https://github.com/user-attachments/assets/c9342e4d-5bee-4175-a0ed-134364b4e526">

## Future Plan
현재의 데모 버전은 AWS CSP 단일 제공자로 운영되고 있습니다. 그러나 향후 AWS뿐만 아니라 Microsoft Azure, Google Cloud Platform(GCP) 등 다양한 클라우드 서비스 제공자들을 지원하기 위한 Terraform 코드를 추가함으로써 CSP에 종속되지 않는 통합 VM 관리 플랫폼으로 발전할 수 있을 것입니다. 이러한 접근은 플랫폼의 유연성을 높이고, 다양한 클라우드 환경에서의 관리 기능을 강화하는 데 기여할 것입니다.

또한, 플랫폼은 Apache Kafka를 기반으로 한 분산형 스트리밍 플랫폼을 메시지 큐 솔루션으로 사용하고 있습니다. 사용자의 환경에 따라 적절한 플랫폼을 선택할 수 있도록, 함께 배포되는 Docker Compose 파일을 제공할 계획입니다. 이를 통해 사용자는 자신에게 최적화된 메시지 큐 플랫폼을 선택하고 배포할 수 있으며, 이로써 더욱 사용자 친화적이고 유연한 오픈소스 솔루션으로 거듭날 수 있을 것입니다.

---
<div align="center">
    <a href="https://github.com/KeepYourCost">
        <img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https://github.com/KeepYourCost" alt="Hits Badge"/>
    </a>
    <a href="https://github.com/KeepYourCost/.github/blob/main/LICENSE">
        <img src="https://img.shields.io/badge/License-MIT-yellow.svg?" alt="License Badge"/>
    </a>
</div>
