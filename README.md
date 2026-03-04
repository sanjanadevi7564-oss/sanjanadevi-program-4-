# Postfix Expression Evaluation using Stack

def evaluate_postfix(expression):
    stack = []

    for ch in expression:
        if ch.isdigit():        # If operand, push to stack
            stack.append(int(ch))
        else:                   # If operator
            b = stack.pop()
            a = stack.pop()

            if ch == '+':
                stack.append(a + b)
            elif ch == '-':
                stack.append(a - b)
            elif ch == '*':
                stack.append(a * b)
            elif ch == '/':
                stack.append(a / b)

    return stack.pop()


# Input
exp = input("Enter Postfix Expression: ")

# Function Call
result = evaluate_postfix(exp)

# Output
print("Result:", result)# sanjanadevi-program-4-
