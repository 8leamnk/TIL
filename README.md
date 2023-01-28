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
`<Component1 />`
) : state2 ? (
`<Component2 />`
) : (
`<Component3 />`
)}
</code>
</pre>

보다는

<pre>
<code>
{state1 && `<Component1 />`}
{state2 && `<Component2 />`}
{!state1 && !state2 && `<Component3 />`}
</code>
</pre>

이렇게 코드를 작성하는 것이 좋다.
