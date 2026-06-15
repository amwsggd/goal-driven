[中文版](readme_cn.md)

# Goal-Driven


The purpose of the Goal-Driven approach is to enable your multi-agent system (e.g., Claude Code, Codex, OpenClaw) to sustain more than 300 hours of continuous effort in solving an extremely complex problem that has a specific objective and a set of strict, well-defined criteria.

Goal-Driven is best suited for tasks that are highly intricate, time-consuming, logically complex, and abstract—yet can be thoroughly evaluated for success. Typical examples include compiler design, mathematical theorem proving, computational problems, database architecture, sophisticated system-level design, and EDA simulation challenges.

The core concepts of Goal-Driven are as follows:

1. Goal – the ultimate objective of the entire system and the central task of all subagents.

2. Criteria – a clear set of conditions that allow the master agent to determine whether the task is completed and the goal has been achieved.

3. Subagent – an agent responsible for continuously working toward solving the problem and achieving the assigned goal.

4. Master Agent – the only controller of subagents, responsible for independently evaluating whether the goal has been reached based on the defined criteria. It acts as the final decision-maker for the system’s process.

The core philosophy of Goal-Driven is straightforward:

1. When the Goal-Driven process starts, the master agent creates a subagent and instructs it to persistently work toward solving the problem and reaching the goal.

2. The master agent periodically checks whether the subagent is active. If the subagent becomes inactive, claims completion, or enters an idle state, the master agent must evaluate the current result according to the criteria. If the result fails to meet the criteria, it commands the subagent to continue working, repeating this cycle until the criteria are satisfied.

3. Once the subagent’s output meets the criteria, the system halts and announces successful completion.

The pseudocode representation of this process is as follows:
```
while (criteria not met)
{
    let the subagent work on solving the problem and achieving the Goal
}
```

## Example of open source projects developed by Goal-Driven system

TypeScript compiler in C++(in ~100 hours) [https://github.com/lidangzzz/TypeScript-C-Implementation-by-OnlySpecs](https://github.com/lidangzzz/TypeScript-C-Implementation-by-OnlySpecs)

SQLite in Rust(in ~30 hours) [https://github.com/lidangzzz/sqlite-rust-by-OnlySpecs](https://github.com/lidangzzz/sqlite-rust-by-OnlySpecs)

Lean4 compiler in TypeScript (in progress) [https://github.com/lidangzzz/Lean4-ts](https://github.com/lidangzzz/Lean4-ts)


## Usage:
Copy the following prompt into your text editor. Carefully fill in the blanks for both goal and criteria, then run it using your multi-agent–supported tool (for example, Claude Code, Codex, OpenClaw, etc.).

## Example:

Goal: [[[[[Write a TypeScript compiler in C++ that correctly transpiles TypeScript into JavaScript, including complete documentation and unit tests.]]]]]

Criteria for success: [[[[[Ensure that the TypeScript compiler successfully compiles and generates 2,000 comprehensive TypeScript test case files covering as many TypeScript syntax features as possible. Confirm that the C++ TypeScript compiler correctly transpiles the code into JavaScript. Then, run both the outputs from this compiler and the official tsc transpiler on Node.js, and verify that the two resulting JavaScript files produce identical outputs.]]]]]


## Notes:

1. I strongly advise not adding this prompt to any AI agent’s skills or plugins, as doing so could contaminate your context window.

2. Goal-Driven processes may consume significant time and LLM tokens; please make sure your AI agent’s API plan or subscription balance is sufficient.



-----

# The Goal-Driven Prompt Template (1 master agent + 1 subagent)

[prompt](https://raw.githubusercontent.com/amwsggd/goal-driven/refs/heads/main/prompt.md)
