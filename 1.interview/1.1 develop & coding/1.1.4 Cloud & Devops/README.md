
- IaC 란 ?
```
IaC(Infrastructure as a code)는 인프라 구성을 Shell 기반 스크립트 등으로 프로그램 처리하는 방식이다.
손쉽고 편리한 구성, 인프라의 확장과 관리가 가능하다.
```

- IaC 도구종류와 사례는?
```
구성조정도구와 구성관리도구가 있다.
구성 조정 도구 (Configuration Orchestration Tool)는 서버 및 인프라 구축의 자동화를 수행하며 Terraform, AWS Cloud formation 등이 있다.
구성 관리 도구 (Configuration Management Tool)는 이미 프로비저닝된 인프라 SW 및 시스템 관리하는 도구로서 Chef,Puppet 등이 있다.
```

- AWS Cloudformation 은???
```
Cloudformation은 Stack을 생성하고, 변경사항을 확인 및 업데이트 하는 것이다.
Stack은 Cloudformation에서 하나의 단위로 관리할 수 있는 AWS리소스 모음이다.
Template은 JSON 또는 YAML 형식으로, 스택에서 프로비저닝할 리소스를 설명하는 파일이다.
```

- Template 의 구성요소는>
```
Resources 섹션과 Output 섹션이 있다.
Resources 섹션은 스택에 포함할 인스턴스나 버킷 등의 AWS리소스 속성값 등을 기입해야되는 필수항목이다. 
Outputs 섹션은 스택생성 혹은 템플릿 실행 결과값을 받을 수 있다.
```
