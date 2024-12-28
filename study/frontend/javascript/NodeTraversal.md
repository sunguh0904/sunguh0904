## JavaScript Node Traversal
> ### 노드 탐색 (node traversal)
요소를 취득한 다음, 취득한 요소를 기점으로 DOM 트리의 노드를 옮겨다니며 부모, 형제, 자식 노드 등을 탐색해야 할 때가 있음</br>
DOM 트리 상의 노드를 탐색할 수 있도록 Node, Element 인터페이스는 트리 탐색 프로퍼티를 제공</br>
노드 탐색 프로퍼티는 모두 참조만 가능한 읽기 전용 접근자 프로퍼티

> ### 자식 노드 (child node)
1. Node.prototype.childNodes: 자식 노드(요소 노드, 텍스트 노드)를 탐색하여 NodeList에 담아 반환
2. Node.prototype.firstChild: 첫 번째 자식 노드(요소 노드, 텍스트 노드) 반환
3. Node.prototype.lastChild: 마지막 자식 노드(요소 노드, 텍스트 노드) 반환
    ```html
    <ol id="node">
        <li>Node.prototype.childNodes : 자식 노드(요소 노드, 텍스트 노드)를 탐색하여 NodeList에 담아 반환</li>
        <li>Node.prototype.firstChild : 첫 번째 자식 노드(요소 노드, 텍스트 노드) 반환</li>
        <li>Node.prototype.lastChild : 마지막 자식 노드(요소 노드, 텍스트 노드) 반환</li>
    </ol>
    ```
    ```javascript
    const $node = document.getElementById('node');
    console.log($node.childNodes); // NodeList 반환, 요소 노드뿐만 아니라 텍스트 노드도 포함
    console.log($node.firstChild); // 첫 번째 자식 노드 탐색
    console.log($node.lastChild); // 마지막 자식 노드 탐색
    ```

4. Element.prototype.children: 자식 노드 중 요소 노드만 탐색하여 HTMLCollection에 담아 반환
5. Element.prototype.firstElementChild: 첫 번째 자식 요소 노드 반환
6. Element.prototype.lastElementChild: 마지막 자식 요소 노드 반환
    ```html
    <ol id="element">
        <li>Element.prototype.children : 자식 노드 중 요소 노드만 탐색하여 HTMLCollection에 담아 반환</li>
        <li>Element.prototype.firstElementChild : 첫 번째 자식 요소 노드 반환</li>
        <li>Element.prototype.lastElementChild : 마지막 자식 요소 노드 반환</li>
    </ol>
    ```
    ```javascript
    const $element = document.getElementById('element');
    console.log($element.children); // HTMLCollection 반환, 요소 노드만 포함
    console.log($element.firstElementChild); // 첫 번째 자식 요소 노드 탐색
    console.log($element.lastElementChild); // 마지막 자식 요소 노드 탐색
    ```

7. Node.prototype.hasChildNodes: 자식 노드 존재 여부를 확인
    ```html
    <ol id="empty"></ol>
    ```
    ```javascript
    const $empty = document.getElementById('empty');
    console.log($node.hasChildNodes()); // true
    console.log($element.hasChildNodes()); // true
    console.log($empty.hasChildNodes()); // 텍스트 노드를 포함하여 확인하므로 개행하면 true, 개행하지 않으면 false
    console.log(!!$empty.children.length); // 텍스트 노드를 제외한 요소 노드의 존재를 확인
    console.log(!!$empty.childElementCount); // 텍스트 노드를 제외한 요소 노드의 존재를 확인
    ```

> ### 부모 노드 (parent node)
1. Node.prototype.parentNode: 부모 노드를 탐색
    ```html
    <ul id="lists">
        <li class="coffee">커피</li>
        <li class="coke">콜라</li>
        <li class="milk">우유</li>
    </ul>
    ```
    ```javascript
    const $coke = document.querySelector('.coke');
    console.log($coke.parentNode); // 부모 노드 탐색
    ```

> ### 형제 노드 (sibling node)
1. Node.prototype.previousSibling: 형제 노드 중 자신의 이전 형제 노드(요소 노드, 텍스트 노드)를 탐색하여 반환
2. Node.prototype.nextSibling: 형제 노드 중 자신의 다음 형제 노드(요소 노드, 텍스트 노드)를 탐색하여 반환
    ```html
    <ol id="node">
        <li>Node.prototype.previousSibling : 형제 노드 중 자신의 이전 형제 노드(요소 노드, 텍스트 노드)를 탐색하여 반환</li>
        <li>Node.prototype.nextSibling : 형제 노드 중 자신의 다음 형제 노드(요소 노드, 텍스트 노드)를 탐색하여 반환</li>
    </ol>
    ```
    ```javascript
    const $node = document.getElementById('node');
    const firstChild = $node.firstChild;
    console.log(firstChild); // 첫 번째 자식 노드 탐색
    const nextSibling = firstChild.nextSibling;
    console.log(nextSibling); // 다음 형제 노드 탐색
    const previousSibling = nextSibling.previousSibling;
    console.log(previousSibling); // 이전 형제 노드 탐색
    ```

3. Element.prototype.previousElementSibling: 형제 요소 노드 중 자신의 이전 형제 요소 노드를 탐색하여 반환
4. Element.prototype.nextElementSibling: 형제 요소 노드 중 자신의 다음 형제 요소 노드를 탐색하여 반환
    ```html
    <ol id="element">
        <li>Element.prototype.previousElementSibling : 형제 요소 노드 중 자신의 이전 형제 요소 노드를 탐색하여 반환</li>
        <li>Element.prototype.nextElementSibling: 형제 요소 노드 중 자신의 다음 형제 요소 노드를 탐색하여 반환</li>
    </ol>
    ```
    ```javascript
    const $element = document.getElementById('element');
    const firstElementChild = $element.firstElementChild;
    console.log(firstElementChild); // 첫 번째 자식 요소 노드 탐색
    const nextElementSibling = firstElementChild.nextElementSibling;
    console.log(nextElementSibling); // 다음 형제 요소 노드 탐색
    const previousElementSibling = nextElementSibling.previousElementSibling;
    console.log(previousElementSibling); // 이전 형제 요소 노드 탐색
    ```

[뒤로](javascript.md)
