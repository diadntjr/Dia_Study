# DFA

## 유한 오토마타

### 그게 뭔데?
<p></p>
이제 본격적으로 오토마타, 그중에서도 유한 오토마타(Finite Automata)에 대해서 나오는데, 오토마타는 저번에도 나왔듯 추상적인 기계장치(Machine)이다. 따라서 유한 오토마타 또한 기계장치를 추상화 시켜놓은 것이며, 그중에서도 **유한한 상태**를 가지는 기계장치이다.

<p>상태(State)란 무엇인가? 말 그대로 현재 기계장치의 상태이다. 우리 몸의 상태가 여러 개가 있듯. 기계장치도 목적에 따라 설계된 여러가지 상태가 있다.</p>

<p>유한 오토마타를 예를 들어 설명하자면, 다음과 같은 유한 오토마타가 존재한다.</p>

<img src="https://bestowing.github.io/assets/img/2020-11-02/automata4/11.png">

<p>다음 오토마타는, 전등 스위치를 추상화한 유한 오토마타이다. 이 유한 오토마타에는 상태가 2개 존재한다. off(0)과 on(1)이다. 각각의 상태가 존재하는 이유는 간단하다. <b>현재 전등이 켜져있는 상태인지, 꺼져있는 상태인지</b>를 기억해야 하기 때문이다. 이처럼 오토마타의 상태는 기계장치의 목적에 따라 다양하고, 유한 오토마타는 <b>유한한 개수</b>의 상태를 가지는 오토마타이다.</p>

<p>여기서 눈여겨 보아야할 것은 바로, <b>화살표</b>이다. 한 상태에서 다른 상태로 전이(transition)되는 것을 표기하기 위해 사용되며, 이는 매우 직관적이다. (화살표에 보이는 push라는 글자는 입력을 뜻한다.) </p>

<p>이처럼 어떤 오토마톤에 특정한 입력이 주어지면, 다른 상태로 전이가 일어난다. 즉, 다음 그림에 따르면, 전등이라는 오토마톤은 push라는 입력이 주어지면(스위치를 누르면) on이라는 상태로 전이되고, 다시 push라는 입력이 주어지면 off라는 상태로 전이되는 것이다.</p>


## 유한 오토마타와 형식언어
<p></p>
<p> 그렇다면 유한 오토마타와 저번에 살폈던 형식언어는 무슨 관계가 있을까?</p>

<p>유한 오토마타는 문자열을 입력으로 받아, 규칙성이 있는지 없는지를 판별한다. 특정 문자열을 입력했을때 유한 오토마타가 이를 받아들인다면(accepted), 그 문자열은 규칙성을 입력받는 것이다.</p>

<p>규칙성에 대해 예를 들자면 01로 끝나거나, 마지막에서 4번째 글자가 a거나, 문자열의 길이가 홀수이다 등등을 이야기한다.</p>