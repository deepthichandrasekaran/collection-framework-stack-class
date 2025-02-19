# collection-framework-stack-class
import java.util.Stack;
public class VerySimpleCalculator {
public static int evaluateExpression(String expression) {

Stack&lt;Integer&gt; stack = new Stack&lt;&gt;();
for (char ch : expression.toCharArray()) {
if (Character.isDigit(ch)) {
// If the character is a digit, push the corresponding integer to the stack
stack.push(Character.getNumericValue(ch));
} else if (ch == &#39;+&#39;) {
// If the character is &#39;+&#39;, pop two operands, add them, and push the result back to
the stack
int operand2 = stack.pop();
int operand1 = stack.pop();
stack.push(operand1 + operand2);
} else if (ch == &#39;-&#39;) {
// If the character is &#39;-&#39;, pop two operands, subtract them, and push the result
back to the stack
int operand2 = stack.pop();
int operand1 = stack.pop();
stack.push(operand1 - operand2);
}
}
// The result should be the only element left in the stack
return stack.pop();
}
public static void main(String[] args) {
String expression = &quot;3 + 4 - 2&quot;;
int result = evaluateExpression(expression);
System.out.println(&quot;Result of the expression &#39;&quot; + expression + &quot;&#39;: &quot; + result);
}
}
Output:
Result of the expression &#39;3 + 4 - 2&#39;: 5
