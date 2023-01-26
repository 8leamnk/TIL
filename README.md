# 2023.01.26

render 쪽에 삼항연산자를 사용할 때
한 번만 사용하는 경우는 가독성 문제가 전혀 없지만 중첩해서 사용하면 가독성에 문제가 크다.
따라서 이런 경우에는 단축평가를 사용하면 된다.
예를 들어,
<code>
{state1 ? (
<Component1 />
) : state2 ? (
<Component2 />
) : (
<Component3 />
)}
</code>
보다는
<code>
{state1 && <Component1 />}
{state2 && <Component2 />}
{!state1 && !state2 && <Component3 />}
</code>
이렇게 코드를 작성하는 것이 좋다.
