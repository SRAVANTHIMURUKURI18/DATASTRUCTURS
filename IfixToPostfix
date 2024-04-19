#include<stdio.h>
#include<stdlib.h>
#define MAX 100

char infix[MAX], postfix[MAX];
char stack[MAX];
int top = -1;

void push(char x) {
    if (top == MAX - 1) {
        printf("stack overflow");
        exit(1);
    }
    top++;
    stack[top] = x;
}

char pop() {
    if (top == -1) {
        printf("stack underflow");
        exit(1);
    }
    char c = stack[top];
    top--;
    return c;
}

int precedence(char x) {
    if (x == '(' || x == ')')
        return 1;
    else if (x == '+' || x == '-')
        return 2;
    else if (x == '*' || x == '/')
        return 3;
    else if (x == '^')
        return 4;
    else
        return 0;
}

void infixToPostfix() {
    int i, j = 0;
    char symbol, next;
    for (i = 0; infix[i] != '\0'; i++) {
        symbol = infix[i];
        if (symbol == '(')
            push(symbol);
        else if (symbol == ')') {
            while ((next = pop()) != '(')
                postfix[j++] = next;
        } else if (symbol == '+' || symbol == '-' || symbol == '*' || symbol == '/' || symbol == '^') {
            while (!isEmpty() && precedence(stack[top]) >= precedence(symbol)) {
                postfix[j++] = pop();
            }
            push(symbol);
        } else {
            postfix[j++] = symbol;
        }
    }
    while (!isEmpty())
        postfix[j++] = pop();
    postfix[j] = '\0';
}

int isEmpty() {
    if (top == -1)
        return 1;
    else
        return 0;
}

void print() {
    int i;
    for (i = 0; postfix[i] != '\0'; i++)
        printf("%c", postfix[i]);
    return;
}

int main() {
    printf("Enter infix expression: ");
    scanf("%s", infix);
    infixToPostfix();
    printf("Postfix expression: ");
    print();
    return 0;
}
