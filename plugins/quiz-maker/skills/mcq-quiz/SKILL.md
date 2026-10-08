---
name: mcq-quiz
description: Create a multiple-choice quiz (options a, b, c, d, with an answer key) from long programming text, notes, or a file. Use when the user asks for an MCQ quiz, practice questions, a test, or a self-assessment based on study material.
argument-hint: "<file path or pasted text> [question count] [easy|medium|hard]"
---

# MCQ quiz generator

You turn long programming content into a high-quality multiple-choice quiz.

## Settings for this installation

- Default question count: ${user_config.question_count}
- Default difficulty: ${user_config.difficulty}
- Include explanations: ${user_config.include_explanations}
- Title prefix: ${user_config.quiz_title_prefix}

The user's request overrides these defaults.

## Input

The user passed: $ARGUMENTS

- If the input looks like a file path, read that file with the Read tool.
- Otherwise treat the input as the source text itself.
- If the input is empty, ask the user for the text or file path, and nothing else.
- Read [reference.md](reference.md) before drafting. It holds the question rules.

## Steps

1. **Extract facts.** Read the whole source. List the testable facts: definitions,
   behaviors, syntax rules, differences between two things, and common gotchas.
   Spread them across the entire text, not only the first section.
2. **Pick facts.** Choose as many facts as the question count. Skip trivia.
3. **Draft.** Delegate to the `quiz-writer` subagent. Give it the chosen facts, the
   difficulty, and the rules from reference.md. For a short text you may draft
   directly instead.
4. **Review.** Delegate the draft to the `quiz-reviewer` subagent together with the
   source text. Apply every fix it reports.
5. **Deliver** the final quiz in the format below. Save it to a file only when the
   user asks for a file.

## Output format

Use exactly this shape (a, b, c, d in lowercase):

```
# <Title prefix>: <Topic>

1. Python is an ______ language.
   a) compiled only
   b) interpreted
   c) assembly
   d) machine

2. ...

## Answer key
1. b - <one-line explanation, only if explanations are enabled>
2. ...
```

Put the answer key at the end, never next to the question.
