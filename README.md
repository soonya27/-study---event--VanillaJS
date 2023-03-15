# -study---event--VanillaJS

## 동적요소 생성 이벤트 위임(Event Delegation) -> MutationObserver사용
# MutationObserver = DOM의 변경을 감시하고, 변화가 있을 때 콜백 함수를 실행함.


### example
```html
//observe(부모요소 바로 아래 자식요소만 인식..)
observerTable.observe(document.querySelector('#mainTable tbody'), { childList: true });
```


### code
```javascript
const observerTable = new MutationObserver(function (mutations) {
    mutations.forEach(function (mutation) {
        mutation.addedNodes.forEach(function (node) {
            //생성되는 요소
            if (node.nodeName === 'TR') {
                node.addEventListener('click', function () {
                    // 처리할 코드 작성
                    console.log('dfdfdf')
                });
            }
        });
    });
});
```
