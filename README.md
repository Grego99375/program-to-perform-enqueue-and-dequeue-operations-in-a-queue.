# program-to-perform-enqueue-and-dequeue-operations-in-a-queue.
program to perform enqueue and dequeue operations in a queue.

#include <stdio.h>
#define SIZE 5

int queue[SIZE];
int front = -1;
int rear = -1;

// Insert an element
void enqueue(int value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow\n");
    }
    else {
        if (front == -1)
            front = 0;

        rear++;
        queue[rear] = value;

        printf("%d inserted\n", value);
    }
}

// Remove an element
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue Underflow\n");
    }
    else {
        printf("%d deleted\n", queue[front]);
        front++;

        if (front > rear) {
            front = rear = -1;
        }
    }
}

// Display queue
void display() {
    int i;

    if (front == -1) {
        printf("Queue is empty\n");
    }
    else {
        for (i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();

    dequeue();

    display();

    return 0;
}
