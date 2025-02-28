# CloudWave 4기 4조 - 비용 낮Chill_guy
---
#### 기한 : 2025/02/07 ~ 2025/02/27
#### 주제 : CGV 자사 앱에서 영화관 광고 동기화 송출 & 실시간 시사회 스트리밍 서비스 제공

### 팀원 소개
| 박세훈 | AWS Media 서비스 , ELK 모니터링 | [GitHub](https://github.com/silver00-psh) |
| 노현민 | IVS 라이브 서비스, ppt 제작, 발표 | [GitHub](https://github.com/lulu010223) |
| 송성민 | Terraform 인프라 구축, DR 구축 | [GitHub](https://github.com/happiness00000) |
| 엄예림 | Terraform 인프라 구축, 모니터링, Karpenter 오토스케일링 | [GitHub](https://github.com/EomYerim) |
| 윤영학 | 앱 UI 구성, Jenkins, IVS 라이브 서비스 | [GitHub](https://github.com/okhi3945) |
| 이주란 | ArgoCD, Jenkins, 개발계 테라폼 구축 | [GitHub](https://github.com/na2neo4) |


---
### 사용한 리소스 목록
![스크린샷 2025-02-28 144734](https://github.com/user-attachments/assets/23ec3f8a-c75a-4b73-be09-d749ff05bcc9)

### 전체 아키텍처
![스크린샷 2025-02-28 145058](https://github.com/user-attachments/assets/04c1d992-0d27-46dc-aa45-c48e92ccd537)

#### 아키텍처 구분: 개발계, 미디어계, 배포계, DR
![스크린샷 2025-02-28 143456](https://github.com/user-attachments/assets/3af48dc5-e27f-465f-bc05-f955297a56ec)

### 세부 아키텍처

#### 1. 개발계
![스크린샷 2025-02-28 145254](https://github.com/user-attachments/assets/1d439cfb-4b2d-486e-ac13-f46454df5140)
개발계 인프라 전체 테라폼으로 구축

#### 2. 미디어계
![스크린샷 2025-02-28 145702](https://github.com/user-attachments/assets/a021fab4-5434-401d-82a2-364040531adc)
람다를 통해 서비스 전체 플로우 자동화

#### 3. 배포계
![스크린샷 2025-02-28 145815](https://github.com/user-attachments/assets/d9601529-ba28-48ab-8d27-91de3a4245aa)
배포계 인프라 전체 테라폼으로 구축

#### 4. DR
배포계와 동일한 인프라 us-west-1(	미국 서부 캘리포니아 북부) region에 구축

---
### 시연 영상
(https://youtu.be/PFDu9vi0sTw?si=KWmiv3g0ks4B7G9b)

---
### 비용 최적화 포인트
#### 1. 사용하지 않는 리소스는 중지/삭제 (Lambda, Slack 활용)
![스크린샷 2025-02-28 150344](https://github.com/user-attachments/assets/0e464584-95a0-4f39-8fa6-6af44662b405)


#### 2. 오픈소스를 활용한 모니터링
![스크린샷 2025-02-28 150404](https://github.com/user-attachments/assets/a611792d-ed15-4d31-bacb-be27cca2bb9c)

#### 3. 비용 임계값 알림 설정
![스크린샷 2025-02-28 150515](https://github.com/user-attachments/assets/a987a17d-51c3-4e49-b99e-e7ab0788d896)
![스크린샷 2025-02-28 150544](https://github.com/user-attachments/assets/6426e64b-563c-4706-8ee6-04b771e097ea)

---
### 보안성 향상 포인트
#### 1. 리소스
**WAF**: 접속 유형 감지, 봇 접근 차단 등의 접근 제어 정책 적용
![스크린샷 2025-02-28 150809](https://github.com/user-attachments/assets/7893f779-e3ca-4ec2-988d-2d49dedf305a)
**IAM**: 최소 권한만 부여하여 보안을 강화
![스크린샷 2025-02-28 150823](https://github.com/user-attachments/assets/9b686bcb-76b8-4754-83c0-900433361ddc)

#### 2. CI/CD 보안검사
**OWASP**: Dependency Check
**SonarQube**: 소스코드 품질 및 보안 취약점 분석
**Trivy**: 컨테이너 이미지의 잠재적 취약점 검출










