Terraform State란? 왜 필요한가?
================================
##### Terraform must store state about your managed infrastructure and configuration. This state is used by Terraform to map real world resources to your configuration, keep track of metadata, and to improve performance for large infrastructures.
> 즉, 진짜 실제 자원들과 내가 작성한 설정파일을 맵핑 시키기 위해, Metadata를 추적하기 위해, 퍼포먼스 향상을 위해 사용됨.    
##### This state is stored by default in a local file named "terraform.tfstate", 
> terraform.tfstate 이름의 로컬 파일로 저장되는 것이 기본.    
##### but it can also be stored remotely, which works better in a team environment
>  팀 단위로 일할 때 원격에 저장될 수 있음. 그래서 우리는 S3에 테라폼 state값을 저장함.     
##### Terraform uses this local state to create plans and make changes to your infrastructure. Prior to any operation, Terraform does a refresh to update the state with the real infrastructure.
> state 값을 사용해서 plan과 인프라에 변화를 줌.    


Terraform State 의 4가지 목적
============================= 
위 내용과 거의 비슷 
------------------
##### Terraform must store state about your managed infrastructure and configuration. This state is used by Terraform to map real world resources to your configuration, keep track of metadata, and to improve performance for large infrastructures.
> 즉, 진짜 실제 자원들과 내가 작성한 설정파일을 맵핑 시키기 위해, Metadata를 추적하기 위해, 퍼포먼스 향상을 위해 사용됨.    
##### This state is stored by default in a local file named "terraform.tfstate", 
> terraform.tfstate 이름의 로컬 파일로 저장되는 것이 기본.    
##### but it can also be stored remotely, which works better in a team environment
>  팀 단위로 일할 때 원격에 저장될 수 있음. 그래서 우리는 S3에 테라폼 state값을 저장함.       
##### Terraform uses this local state to create plans and make changes to your infrastructure. Prior to any operation, Terraform does a refresh to update the state with the real infrastructure.
> state 값을 사용해서 plan과 인프라에 변화를 줌.    

Terraform import 
=================
#### Terraform is able to import existing infrastructure. This allows you take resources you've created by some other means and bring it under Terraform management.
> 다른 방법으로 만들었던 리소스들을 테라폼 관리 아래에 둘 수 있게 함
#### The current implementation of Terraform import can only import resources into the state. It does not generate configuration. A future version of Terraform will also generate configuration.
> Terraform import는 현재의 State 만 가지고 온다. 설정 파일을 만들지 않는다, 미래에는 테라폼이 설정파일도 만들어 준다고 한다!!! (thumbs up)

### 언제 사용하는가?
> AWS 콘솔에는 생성되어 있는 리소스이고, 테라폼으로 코드화가 되지 않은 경우
> 더이상 콘솔 작업을 추가 하지 않고, 해당 AWS 리소스를 테라폼 코드로 수정하려고 할 때,
> 테라폼 설정 파일로 정의 하고, terraform import를 사용해서, AWS에 생성된 리소스를 state로 가져온다. 
