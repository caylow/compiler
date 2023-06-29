# Bison and Flex Compiler
## A simple lexing and parser using Bison and Flex for grammar.
This project is built in order to show a simple example of how you can make a lexing and a parser using Bison and Flex.
What is expected the code of this project should do given an expression as an input:
1. Show a table of chunks of the expression with its associated token.
2. Check if an expression matches or not the grammar.
3. Show the derivative tree associated with the expression.
It will use the following grammar on EBNF:
```
COMBINABLE_CONDITION::= USE_STATEMENT | {NEGATED_SIMPLE_CONDITIONS}* | {ABBREVIATED_COMBINED_RELATION_CONDITIONS}+
USE_STATEMENT::= "USE" ["FOR"] "DEBUGGING" ["ON"] ({PROCEDURE_NAME}+ | "ALL" "PROCEDURES")
PROCEDURE_NAME ::= ID
NEGATED_SIMPLE_CONDITIONS ::= "!(" SIMPLE_CONDITION ")"
SIMPLE_CONDITION ::= EXPRESSION ("<=" | ">=" | "<" | ">" | "==" | "!=" | "&&" | "||" ) EXPRESSION
ABREVIATED_COMBINED_RELATION_CONDITIONS ::= EXPRESSION "?" SIMPLE_CONDITION ":" SIMPLE_CONDITION
PROCEDURES_NAMES::= PROCEDURE_NAME | PROCEDURE_NAME PROCEDURES_NAMES
EXPRESSION ::= ID | LITERAL
LITERAL ::= "\""({[a-zA-Z]|["_"]|[0-9]}+)"\""
ID ::= ([a-zA-Z]|["_"])({[a-zA-Z]|["_"]|[0-9]}*)
```
