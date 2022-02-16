# PlantUML PLUGIN
### 개발을 함에 있어 코드가 너무 방대해서 따라가기가 벅차거나, 내가 쓴 코드가 아니라 분석이 필요할 때가 있다.
### 이 분석을 할 때, 나 혼자 보는 경우면 상관이 없지만, 회사에서는 특히 문서화/시각화 하는 것을 좋아한다.
### 그럴 때 이 분석 자료(Sequence Diagram)을 쉽게 그려줄 수 있는 Tool, **PlantUML** 을 소개하고자 한다.

### 설치 방법.

1. 글쓴이는 이미 installed이지만, 간단히 Settings >> Plugins >> 'plantuml'검색 후 install 하면 된다.
> ![image](https://user-images.githubusercontent.com/49303504/154176433-e5a0aa47-664a-466e-957e-c494b17bdc43.png)

### 사용 방법

#### 당연히 이런 저런 기능이 많겠지만, Sequence Diagram에 초점을 맞추고, 그 중에서도 제일 많이 쓰이는 Grammar를 간단히 소개하고자 한다.
- Actor, Participant
> Sequence Diagram이기에 당연히 Actor와 Participant이 존재한다.
> > 선언하는 방법은 매우 쉽다. 
> > 'actor 이름', 'participant 이름 as 표시법'
> > 간단 표시법으로 나중에 해당 participant를 빠르게 표시할 수 있다.
> > 
> > ![image](https://user-images.githubusercontent.com/49303504/154177339-fb2f596f-2cce-40ba-be37-24ddf7b0d1e1.png)

- 전체 그림 세팅하기 (skinparam)
> 전체적인 그림 세팅을 하는 방법(배경, 쉐도우, 색, 글씨크기 등등)도 여러가지가 있다.
> 그 중에서 글쓴이가 생각하는 필요한 몇 가지를 소개한다. 쓰는 방법은 'skinparam 세팅하고자하는것 값'이다.
> > sequenceArrowThickness는 sequence를 나타낼 방향선의 굵기를 설정해준다.
> > roundcorner는 participant 칸을 둥글게 만들어준다 (뭔가 더 있어보임)
> > 
> > ![image](https://user-images.githubusercontent.com/49303504/154177844-fcd42ee2-597e-4500-9aba-a357994f8902.png)

- 방향선
> A가 B한테 무엇을 보낼때(A가 무엇을 함에 있어서 B에게 전달될 때) 방향선을 쓴다.
> > 선의 종류에 따라 쓰는 방법이 다르다.
> > 여기서 주의!! 선의 종류가 여러가지 있지만 그 선의 종류마다 특정한 의미를 가지지는 않는다.
> > 다시 말해, 실선과 점선의 정의가 따로 있지 않다. 만드는 사람이 먼저 정의를 해줌에 따라 마음대로 쓸 수 있다는 뜻.
> > 실선의 경우 '이름 -> 이름'
> > 점선의 경우 '이름 --> 이름'으로 표시할 수 있다.
> > 
> > ![image](https://user-images.githubusercontent.com/49303504/154178586-4d9ea93c-feb5-41e7-bedf-bc7b05d1cd1c.png)
> > 이 예시에서는 실선은 공식적으로 말한 것, 점선은 몰래 얘기한 것으로 정의하였다.
>
> 방향선에 색을 입힐 수도 있다.
> > '->'에서 -와 > 사이에 색([#blue], [#red] 등등)을 넣어주면 된다.
> > 
> > ![image](https://user-images.githubusercontent.com/49303504/154179188-df4ddc4f-897e-44a8-badf-c3f20232e7c6.png)

- Activate
> Class Sequence Diagram의 경우, 해당 Class가 언제부터 활성화가 되고, 언제 비활성화가 되는지 표시하는 것도 중요하다.
> > 'Activate 이름', 'Deactivate 이름'으로 표시할 수 있다.
> > 
> > ![image](https://user-images.githubusercontent.com/49303504/154178861-67feba7c-7ddd-4ea7-be0b-747de4e90f30.png)
