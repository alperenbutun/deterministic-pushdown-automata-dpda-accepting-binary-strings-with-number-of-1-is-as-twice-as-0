Deterministic Pushdown Automaton (DPDA) Accepting Binary Strings With Number of 1s is as Twice as 0

**Update (April 10, 2024):**
It's a fact that 1,1/E condition defined for the "top left node" is never happening.

**Update (June 11, 2024):**
What made me think about this problem is fundamental in Computer Science is that:
DPDAs are first introduced in the late 1960s. I think the correct date is 1967. I think this problem has the highest priority after "accepting binary strings with number of 1s is equal to number of 0s". If there is no solution until now, I thought it would be valuable when I solved it and shared. In addition, some points I saw in my solution made me think that it shouldn't be solved before + my solution is correct and valuable.

The first of the points is that there is a need for searching the memory according to the character seen from the input string. However, searching the memory is not trivial. We can't know how many characters are there and building a deterministic pda seems like impossible. But I kept the characters in the memory in a way that: If there is "0" or "1" in the string that will be kept in the memory, it is the first or the second character. (can be seen in the design). Therefore, checking the first two characters of the memory is sufficient to decide if there is "0" or "1" in the memory. So It's checking only the first two characters of the memory to fully search the memory for a character. In short, Memory searching problem is reduced to Memory checking problem.

The second point is that, although my solution mechanism mentioned above is logical and working correctly, it was failing for ~1% percent of inputs. For those inputs, the below condition was happening and machine was halting with failure.

**Current Operation string: 100000000
Current Memory condition: 000000001**

If the condition was Current Operation string: 100000000 and Current Memory condition: 100000000 (which is in fact, meaning the same with the paradox above: the operation string satisfies the memory condition(needs)) there would be no problem but the first condition was a paradox for my solution. So I carefully checked the "1% percent" and saw that the total of 1% failure is only about the paradox, nothing else. So I added the "top left node" and solved it.

This solution is deterministic so it can be applied to real world. It's 2-step solution. There is a paradox so it can be thought "impossible to solve". I shared a solution. It can be valuable and a contribution to the computer science.

Test File:
[Please Click here to Run the Test File](https://rawcdn.githack.com/alperenbutun/Deterministic-PushDown-Automata-DPDA-Accepting-Binary-Strings-with-Number-of-1-is-as-Twice-as-0/0adb4c3/Auto%20Testing.html)
