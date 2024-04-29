# Linked List

## List Struct

```c
struct node {
    int data;
    struct node* next;
};
```

## Insert Node from front

```c
void insertFront(struct node **head, struct node **tail, int data){

    struct node* temp = (struct node*)malloc(sizeof(struct node));

    if (*head == NULL){
        temp->data = data;
        temp->next = NULL;
        *head = temp;
        *tail = temp;
    }
    else {
        temp->data = data;
        temp->next = *head;
        *head = temp;
    }

    return;

}
```

## Insert Node from back

```c
void insertBack(struct node **head, struct node **tail, int data){

    struct node* temp = (struct node*)malloc(sizeof(struct node));

    if (*head == NULL){
        temp->data = data;
        temp->next = NULL;
        *head = temp;
        *tail = temp;
    }
    else {
        temp->data = data;
        temp->next = NULL;
        (*tail)->next = temp;
        *tail = (*tail)->next;
    }

    return;

}
```

## Remove Node from front

```c
void removeFront(struct node **head, struct node **tail){
    
    if (*head == NULL){
        return;
    }
    else {
        struct node *temp = *head;
        *head = (*head)->next;
        free(temp);
    }

    return;

}
```

## Remove Node from back

```c
void removeBack(struct node **head, struct node **tail){

    if (*head == NULL){
        return;
    }
    else {
        struct node *temp = *tail;
        struct node *itr = *head;

        while (itr->next != *tail){
            itr = itr->next;
        }

        itr->next = NULL;
        *tail = itr;
        free(temp);
    }

    return;

}
```

## Print all Nodes

```c
void printList(struct node *head){
    struct node *itr = head;
    while (itr != NULL) {
        printf("%d ", itr->data);
        itr = itr->next;
    }
    printf("\n");
    return;
}
```

## Swap nodes in Linked List by index (start from 0)

```c
// Function to swap two nodes in a linked list based on their indices
void swapNodesByIndex(struct node **head, int index1, int index2) {
    // If indices are the same, no need to swap
    if (index1 == index2)
        return;

    // Initialize pointers to track the previous and current nodes of the nodes to be swapped
    struct node *prevX = NULL, *currX = *head;
    struct node *prevY = NULL, *currY = *head;

    // Traverse the list to find the nodes at the given indices
    for (int i = 0; currX != NULL && i < index1; i++) {
        prevX = currX;
        currX = currX->next;
    }
    for (int i = 0; currY != NULL && i < index2; i++) {
        prevY = currY;
        currY = currY->next;
    }

    // If either index is out of bounds or nodes not found, return
    if (currX == NULL || currY == NULL)
        return;

    // If x is not the head of the list
    if (prevX != NULL)
        prevX->next = currY;
    else // Make y the new head
        *head = currY;

    // If y is not the head of the list
    if (prevY != NULL)
        prevY->next = currX;
    else // Make x the new head
        *head = currX;

    // Swap next pointers of x and y
    struct node *temp = currY->next;
    currY->next = currX->next;
    currX->next = temp;
}
```