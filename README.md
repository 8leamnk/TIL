# 2023.02.01

<code>splice()</code>와 <code>slice()</code>의 차이점

### <code>splice()</code>

1. 원본이 바뀐다.
   splice()를 호출한 결과, 원본 example을 출력한 결과는 제거한 원소가 없어진 상태이다.
2. return 값은 자른 원소들로 이루어진 배열이다.

### <code>slice()</code>

1. 원본이 바뀌지 않는다.
   slice()를 호출한 결과, 원본 example을 출력한 결과는 그대로이다.
2. return 값은 자른 원소들로 이루어진 배열이다.

# 2023.01.27

<code>Object.key()</code> 를 이용하여 객체가 비어있는지 확인할 수 있다.

<pre>
<code>
const object1 = {
  a: 'somestring',
  b: 42,
  c: false
};
</code>
</pre>

<code>Object.key(object1).length</code> 의 값으로 객체가 비어있는지 아닌지 확인이 가능하다.

# 2023.01.26

render 쪽에 삼항연산자를 사용할 때
한 번만 사용하는 경우는 가독성 문제가 전혀 없지만 중첩해서 사용하면 가독성에 문제가 크다.
따라서 이런 경우에는 단축평가를 사용하면 된다.
예를 들어,

<pre>
<code>
{state1 ? (
  '컴포넌트1'
) : state2 ? (
  '컴포넌트2'
) : (
  '컴포넌트3'
)}
</code>
</pre>

보다는

<pre>
<code>
{state1 && '컴포넌트1'}
{state2 && '컴포넌트2'}
{!state1 && !state2 && '컴포넌트3'}
</code>
</pre>

이렇게 코드를 작성하는 것이 좋다.
