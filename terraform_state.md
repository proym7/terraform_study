Terraform State란? 왜 필요한가?
================================
Terraform must store state about your managed infrastructure and configuration. This state is used by Terraform to map real world resources to your configuration, keep track of metadata, and to improve performance for large infrastructures.
> 즉, 진짜 실제 자원들과 내가 작성한 설정파일을 맵핑 시키기 위해, Metadata를 추적하기 위해, 퍼포먼스 향상을 위해 사용됨. 
This state is stored by default in a local file named "terraform.tfstate", 
> terraform.tfstate 이름의 로컬 파일로 저장되는 것이 기본.
but it can also be stored remotely, which works better in a team environment
>  팀 단위로 일할 때 원격에 저장될 수 있음. 그래서 우리는 S3에 테라폼 state값을 저장함.  
Terraform uses this local state to create plans and make changes to your infrastructure. Prior to any operation, Terraform does a refresh to update the state with the real infrastructure.
> state 값을 사용해서 plan과 인프라에 변화를 줌.


Terraform State 의 4가지 목적
============================= 
위 내용과 거의 비슷 
------------------
Terraform must store state about your managed infrastructure and configuration. This state is used by Terraform to map real world resources to your configuration, keep track of metadata, and to improve performance for large infrastructures.
> 즉, 진짜 실제 자원들과 내가 작성한 설정파일을 맵핑 시키기 위해, Metadata를 추적하기 위해, 퍼포먼스 향상을 위해 사용됨. 
This state is stored by default in a local file named "terraform.tfstate", 
> terraform.tfstate 이름의 로컬 파일로 저장되는 것이 기본.
but it can also be stored remotely, which works better in a team environment
>  팀 단위로 일할 때 원격에 저장될 수 있음. 그래서 우리는 S3에 테라폼 state값을 저장함.  
Terraform uses this local state to create plans and make changes to your infrastructure. Prior to any operation, Terraform does a refresh to update the state with the real infrastructure.
> state 값을 사용해서 plan과 인프라에 변화를 줌.

