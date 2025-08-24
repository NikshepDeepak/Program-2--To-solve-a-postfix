# Program-2--To-solve-a-postfix

def evaluate_postfix(expression):
    stack = []

    for ch in expression:
        if ch.isdigit():  # If operand, push to stack
            stack.append(int(ch))
        else:
            # Operator: pop two operands
            operand2 = stack.pop()
            operand1 = stack.pop()

            if ch == '+':
                result = operand1 + operand2
            elif ch == '-':
                result = operand1 - operand2
            elif ch == '*':
                result = operand1 * operand2
            elif ch == '/':
                result = operand1 / operand2

            stack.append(result)

    return stack.pop()


