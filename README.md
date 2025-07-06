# Strider Flows

**Strider Flow** is a way to structure workflows as **linear segments** called **Striders**.  
Each Strider is a reusable tract of Steps that shares context and can chain to other Striders to form a complete process.

## What is a Strider?

A **Strider** is:
- A strictly **linear sequence of Steps**, executed one after another.
- It maintains a **Context** to store and pass data between Steps.
- It can end, or its Steps can perform operations like jumping to another Strider.

A Strider has:
- **ID**: Unique identifier.
- **Name**: Human-readable name.
- **Description**: (Optional) Short explanation.
- **Steps[]**: Ordered list of Steps.

---

## What is a Step?

A **Step** is the smallest unit inside a Strider.

Each Step:
- Has access to the **Context**, which holds any data relevant to the Flow, including results from previous Steps.
- Executes an **Operation** that can read or update the Context.
- Automatically produces a **Result**, which is saved into the Context by default.
- May add or modify other arbitrary data in the Context.
- May include a jump to another Strider as part of its Operation.

A Step typically has:
- **ID**: Unique within its Strider.
- **Description**: What this Step does.
- **Condition**: (Optional) Expression to decide if the Step runs.
- **Operation**: The action to perform (may include a jump as part of its logic).
- **Parameters**: (Optional) Values required by the Operation.
- **Result**: The output produced.

---

## What is Context?

**Context** is the shared memory during a Strider’s execution.  
- Stores inputs, results, and any variables that Steps need.
- Ensures data flows naturally between Steps.
- If a Step jumps to another Strider, the Context can be passed or merged.

---

## What is a Strider Flow?

A **Strider Flow** is a workflow structure built from multiple **Striders**, each representing a strictly linear tract of Steps.

- Each Strider runs its Steps in order, reading and writing to a shared **Context**.
- Execution starts from a **defined initial Strider**.
- Steps decide explicitly if and where to jump next. There is **no automatic execution order** across Striders.
- If no Step triggers a jump, the Flow ends by design — there are no implicit transitions.

This ensures that Striders are **not just static containers** but active, predictable segments that control how the Flow moves forward.  
Without explicit jumps, Striders are never executed arbitrarily.

A Strider Flow is **engine-agnostic** and can be implemented inside any process engine, pipeline, or orchestration framework.

---

## When to use Strider Flows

Use Strider Flows to:
- Make workflows modular, predictable, and easy to test.
- Break complex logic into clear, reusable linear tracts.
- Control process transitions explicitly through Steps, never implicitly.

---

## License

MIT — free to use, modify, and extend.

---

**Author:** [Rafa Rodriguez](https://rafageist.com)
