## Binary Tree Level Order Traversal (Medium)

```javascript
var levelOrder = function(root) {
    let queue = new Deque();
    queue.push(root);
    let result = [];

    while (queue.length) {
        let levelSize = queue.length;
        let currLevel = [];

        for (let i =0; i < levelSize; i++) {
            currNode = queue.shift();
            currLevel.push(currNode);

            if (currNode.left !== null) {
                queue.push(currNode.left);
                };
            if (currNode.right !== null) {
                queue.push(currNode.right);
                };
        };
        result.push(currLevel);
    };
    return result;
};
```
