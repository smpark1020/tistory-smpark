## 문제 설명
N-ary 트리 후위탐색

n-ary 트리의 ```root```가 주어진다. 후위탐색 결과를 리턴해라.

Nary-Tree는 레벨 순으로 초기화 된다. 각 그룹의 자식노드는 null로 구분된다.

## 내가 푼 코드
```
public List<Integer> postorder(Node root) {
    List<Integer> result = new ArrayList<>();
    if (root != null) {
        recursion(root, result);
    }
    
    return result;
}

private void recursion(Node node, List<Integer> result) {
    if (node.children == null) {
        result.add(node.val);
        
        return;
    }
    
    for (Node child : node.children) {
        recursion(child, result);
    }
    
    result.add(node.val);
}
```
* 시간 복잡도: O(n)
* 공간 복잡도: O(n)

## Reference
* [문제](https://leetcode.com/problems/n-ary-tree-postorder-traversal/)
* [내가 푼 코드](https://github.com/smpark1020/leetcode-practice/blob/master/src/leetcode/tree/Q590.java)