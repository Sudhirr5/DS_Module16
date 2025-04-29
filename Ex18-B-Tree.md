# Ex18 B-Tree
### DATE: 27/03/2025
## AIM:
To write a C function to delete an element in a B Tree.
## Algorithm
1. Start the program
2. Try to delete the item from the node using delValFromNode. If not found, print "Not present" and return. 
3. If the node's count is 0 after deletion, set tmp to the current node and update myNode to its first linker child. 
4. Free the tmp node. 
5. Update the global root to the new myNode. 
6. Return after deletion. 
7. End the program 

## Program:
```
Program to write a C function to delete an element in a B Tree
Developed by: SUDHIR KUMAR. R
RegisterNumber: 212223230221
```
```
/* 
struct BTreeNode { 
    int item[MAX + 1], count; 
    struct BTreeNode *linker[MAX + 1]; 
}; 
struct BTreeNode *root; 
*/

void delete(int item, struct BTreeNode *myNode) {
    struct BTreeNode *tmp;
    if (!delValFromNode(item, myNode)) {
        printf("Not present\n");
        return;
    } else {
        if (myNode->count == 0) {
            tmp = myNode;
            myNode = myNode->linker[0];
            free(tmp);
        }
    }
    root = myNode;
    return;
}
```
## Output:

![image](https://github.com/user-attachments/assets/2111cbc9-9f6f-4716-bd2a-7ea613913b36)

## Result:
Thus, the C function to delete an element in a B Tree is implemented successfully.
