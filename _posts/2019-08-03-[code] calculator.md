---
layout: post
title:  "[Code] calculator"
date:   2019-08-03 15:51:00 +0800
categories: code
---
This is a `code` page.


{% highlight python %}
# Python code window
import operator

MAX_INDEX = 99999

def calc(operand1, mid, operand2):
    ops = {
        "+": operator.add,
        "-": operator.sub,
        "*": operator.mul,
        "/": operator.truediv,
        "**": operator.pow
    }
    return ops[mid](float(operand1), float(operand2))    

def run(ops, *signs):
    pos = min([ops.index(s) if s in ops else MAX_INDEX for s in signs])

    while pos < MAX_INDEX:
        result = calc(*ops[pos - 1:pos + 2])
        del ops[pos - 1:pos + 1]
        ops[pos - 1] = result

        pos = min([ops.index(s) if s in ops else MAX_INDEX for s in signs])

    return ops

def split_ops(formular):
    # operand, operator 각각 분리해서 리스트로 저장.
    ops, digit, signs = [], '', ''

    for c in list(formular.replace(' ', '')):
        if not c.isdigit():
            ops.append(digit)
            signs += c
            digit = ''
        else:
            ops.append(signs)
            digit += c
            signs = ''

    ops.append(digit)
    ops.remove('')

    return ops

# formular = '12+2**2*34*111*10+12+34*111*10/12+34*111*10*12+34*111*10-12+34*111*10'
formular = input('수식 입력: ')
ops = split_ops(formular)

# 우선순위 계산 **, *, /, +, -
ops = run(ops, "**")
ops = run(ops, "*", "/")
ops = run(ops, "+", "-")

print(f"계산결과는 {ops}")

{% endhighlight %}

Check out the [Jekyll docs][blog]
[blog]: https://laftworld.github.io
