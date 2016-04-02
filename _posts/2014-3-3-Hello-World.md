---
layout: post
title: Hello, World!
---

print()는 내용을 화면에 보여달라는 명령어
> print("Hello, World!")

"print" statement
*********************

   print_stmt ::= "print" ([expression ("," expression)* [","]]
                  | ">>" expression [("," expression)+ [","]])

"print" evaluates each expression in turn and writes the resulting
object to standard output (see below).  If an object is not a string,
it is first converted to a string using the rules for string
conversions.  The (resulting or original) string is then written.  A
space is written before each object is (converted and) written, unless
the output system believes it is positioned at the beginning of a
line.  This is the case (1) when no characters have yet been written
to standard output, (2) when the last character written to standard
output is a whitespace character except "' '", or (3) when the last
write operation on standard output was not a "print" statement. (In
some cases it may be functional to write an empty string to standard
output for this reason.)

"print" 는 (아래 참조) 각 표현을 차례적으로 평가하고 객체의 표준 출력의 결과를 나타낸다. 객체가 문자열이 아닌 경우, 문자열은 먼저 문자열 전환 규칙에 따라 전환된다. (resulting or original) 문자열이 쓰여진다. 공백은 개별 객체 앞에 쓰이며 출력 시스템은 줄의 시작에 위치한다고 여긴다.

This is the case (1) when no characters have yet been written
to standard output, (2) when the last character written to standard
output is a whitespace character except "' '", or (3) when the last
write operation on standard output was not a "print" statement. (In
some cases it may be functional to write an empty string to standard
output for this reason.)

Note: Objects which act like file objects but which are not the
  built-in file objects often do not properly emulate this aspect of
  the file object's behavior, so it is best not to rely on this.
노트 : 내장된 파일 객체가 아닌데 파일 객체처럼 동작하는 객체는 파일 객체의 행동을 제대로 모방하지 않으므로 파일 객체 의존하지 않는 것이 가장 좋다.


"'\n'"은 "print" 문이 마침표로 끝나는 경우 외에 문자열의 마지막에 쓰인다. 코드 내용에 "print"라는 코드가 포함되어있을 때만 한해서 쓴다.  unless the "print" statement
ends with a comma.  This is the only action if the statement contains
just the keyword "print".

Standard output is defined as the file object named "stdout" in the
built-in module "sys".  If no such object exists, or if it does not
have a "write()" method, a "RuntimeError" exception is raised.
표준 출력은 내장된 "sys" 모듈 안의 "stdout" 라는 이름의 파일 객체로 정의되어 있다. 이 객체가 존재하지 않는 않거나 "wirte()" 메서드가 없을 때 "RuntimeError" 가 발생한다.

"print" also has an extended form, defined by the second portion of
the syntax described above. This form is sometimes referred to as
""print" chevron." In this form, the first expression after the ">>"
must evaluate to a "file-like" object, specifically an object that has
a "write()" method as described above.  With this extended form, the
subsequent expressions are printed to this file object.  If the first
expression evaluates to "None", then "sys.stdout" is used as the file
for output.

"print" 는 확장된 폼또한 갖고 있다. 위에서 설명한 두번째 부분에서 정의된 형태이다. 이 폼은 종종 ""print" chevron."과 폼에서 언급된다. 이 폼에서, ">>" 다음 첫번째 표현은 "파일 같은" 객체를 반드시 평가하며 특히 위에서 설명한 "wirte()" 메서드를 가지는 객체들이 
