## JavaScript Node Properties
> ### 노드 정보 취득 (get node info)
1. Node.prototype.nodeType: 노드 객체의 종류, 즉 노드 타입을 나타내는 상수 반환
    - Node.ELEMENT_NODE: 요소 노드 타입을 나타내는 상수 1 반환
    - Node.TEXT_NODE: 텍스트 노드 타입을 나타내는 상수 3 반환
    - Node.DOCUMENT_NODE: 문서 노드 타입을 나타내는 상수 9 반환
2. Node.prototype.nodeName: 노드의 이름을 문자열로 반환
    - 요소 노드: 다문자 문자열로 태그 이름을 반환
    - 텍스트 노드: 문자열 `#text`를 반환
    - 문서 노드: 문자열 `#document`를 반환
    ```html
    <div id="area">노드 정보 취득</div>
    ```
    ```javascript
    console.log(document.nodeType); // 9
    console.log(document.nodeName); // #document
    const $area = document.getElementById('area');
    console.log($area.nodeType); // 1
    console.log($area.nodeName); // DIV
    const $textNode = $area.firstChild;
    console.log($textNode.nodeType); // 3
    console.log($textNode.nodeName); // #text
    ```

> ### 요소 노드의 텍스트 조작 (text node content)
1. Node.prototype.nodeValue: setter와 getter가 모두 존재하는 접근자 프로퍼티
    - nodeValue 프로퍼티 참조 시 노드 객체의 값(텍스트 노드의 텍스트)을 반환
    - 텍스트 노드가 아닌 노드(문서 노드, 요소 노드)의 경우 null을 반환
    - 텍스트 노드의 nodeValue 프로퍼티에 값을 할당하면 텍스트 노드의 값을 변경할 수 있음
    ```html
    <div id="area">nodeValue</div>
    ```
    ```javascript
    console.log(document.nodeValue); // null
    const $area = document.getElementById('area');
    console.log($area.nodeValue); // null
    const $textNode = $area.firstChild;
    console.log($textNode.nodeValue); // nodeValue
    $textNode.nodeValue = '텍스트 값 변경 완료!';
    ```

2. Node.prototype.textContent: setter와 getter 모두 존재하는 접근자 프로퍼티로서 요소 노드의 텍스트와 모든 자손 노드의 텍스트를 모두 취득하거나 변경
    - 요소 노드의 textContent 프로퍼티를 참조하면 요소 노드의 콘텐츠 영역 내의 텍스트를 모두 반환하며 이 때 HTML 마크업은 무시됨
    - 요소 노드의 textContent 프로퍼티에 문자열을 할당하면 요소 노드의 모든 자식 노드가 제거되고 할당한 문자열이 텍스트로 추가됨. 이 때도 HTML 마크업은 무시되고 문자열 텍스트로 취급됨
    ```html
    <div id="area2">textContent<span>내부 span</span></div>
    ```
    ```javascript
    const $area2 = document.getElementById('area2');
    console.log($area2.textContent); // textContent내부 span
    console.log($area2.nodeValue); // null
    console.log($area2.firstChild.nodeValue); // textContent
    console.log($area2.lastChild.firstChild.nodeValue); // 내부 span
    $area2.textContent = '텍스트 값 변경 완료!<span>내부 span</span>';
    ```

> ### 왜 사용해야 하는가?
1. **노드 정보 확인**: 노드의 타입과 이름을 확인하여 노드의 종류를 파악할 수 있음
2. **텍스트 조작**: 요소 노드의 텍스트를 쉽게 조작할 수 있음

> ### 쉬운 요약
1. nodeType과 nodeName 프로퍼티를 사용하여 노드의 타입과 이름을 확인할 수 있음
2. nodeValue와 textContent 프로퍼티를 사용하여 요소 노드의 텍스트를 조작할 수 있음

> ### 비유
1. 신분증
    - nodeType과 nodeName 프로퍼티는 "노드의 신분증"과 같음
    - 예: 신분증을 통해 사람의 신분을 확인하는 것처럼, nodeType과 nodeName을 통해 노드의 종류를 확인

2. 편집기
    - nodeValue와 textContent 프로퍼티는 "텍스트 편집기"와 같음
    - 예: 편집기를 사용하여 텍스트를 수정하는 것처럼, nodeValue와 textContent를 사용하여 요소 노드의 텍스트를 조작

[뒤로](javascript.md)
