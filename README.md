Deterministic Pushdown Automaton (DPDA) Accepting Binary Strings With Number of 1s is as Twice as 0

**Update (April 10, 2024):**
It's a fact that 1,1/E condition defined for the "top left node" is never happening.

**Update (June 11, 2024):**
What made me think about this problem is fundamental in Computer Science is that:
DPDAs are first introduced in the late 1960s. I think the correct date is 1967. Since that time, It is introduced to every CS student in universities. I think this problem has the highest priority after "accepting binary strings with number of 1s is equal to number of 0s". Therefore, I thought every cs student, even the founders of dpda tried to solve this problem. If there is no solution until now, I thought it would be valuable when I solved it and shared. In addition, some points I saw in my solution made me think that it shouldn't be solved before + my solution is correct and valuable.

The first of the points is that there is a need for searching the memory according to the character seen from the input string. However, searching the memory is not trivial. We can't know how many characters are there and building a deterministic pda looks like impossible. But I kept the characters in the memory in a way that: If there is "0" or "1" in the string that will be kept in the memory, it is the first or the second character. (can be seen in the design). Therefore, checking the first two characters of the memory is sufficient to decide if there is "0" or "1" in the memory. It's checking only the first two characters of the memory to search. In short, Memory searching problem is reduced to Memory checking problem.

The second point is that, although my solution mechanism mentioned above is logical and working correctly, it was failing for ~1% percent of inputs. For those inputs, the below condition was happening and machine was halting with failure.

**Current Operation string: 100000000
Current Memory condition: 000000001**

If the condition was

Current Operation string: 100000000
Current Memory condition: 100000000
(which is in fact, meaning the same with the dilemma above = memory condition satisfies the operation string)

there would be no problem but the first condition was a dilemma for my solution mechanism. So I carefully checked the "1% percent" and saw that the 1% failure is only about the dilemma mentioned above. So I added the "top left node" and solved it.

This solution is deterministic so it can be applied to real world. It's 2-step solution. There is a dilemma so it can be thought "impossible to solve". In addition, when I look from above, there is "removing corresponding zeros" not "ones" so it can be seen like "number zipping" and/or "transforming numbers" while solving the problem. 

I think Math was thinking that this problem is NP-Complete but I shared a solution for it. Therefore, I think it's valuable and a contribution to the computer science.

Test File:
[Please Click here to Run the Test File](https://rawcdn.githack.com/alperenbutun/Deterministic-PushDown-Automata-DPDA-Accepting-Binary-Strings-with-Number-of-1-is-as-Twice-as-0/0adb4c3/Auto%20Testing.html)
