# Strider Flows

**Strider Flow** is a way to structure workflows as **linear segments** called **Striders**.  
Each Strider is a reusable tract of Steps that shares context and can chain to other Striders to form a complete process.

---

## 🔗 What is a Strider?

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

## 🧩 What is a Step?

A **Step** is the smallest unit inside a Strider.

Each Step:
- Receives **input**: from Context or the result of the previous Step.
- Executes a predefined **Operation**: logic that can read/update Context, process data, or even jump to another Strider.
- Produces a **Result**: which can be used by the next Step or saved to Context.

A Step typically has:
- **ID**: Unique within its Strider.
- **Description**: What this Step does.
- **Condition**: (Optional) Expression to decide if the Step runs.
- **Operation**: The action to perform (may include a jump as part of its logic).
- **Parameters**: (Optional) Values required by the Operation.
- **Result**: The output produced.

---

## 📦 What is Context?

**Context** is the shared memory during a Strider’s execution.  
- Stores inputs, results, and any variables that Steps need.
- Ensures data flows naturally between Steps.
- If a Step jumps to another Strider, the Context can be passed or merged.

---

## ⚙️ What is a Strider Flow?

A **Strider Flow** is the orchestration of multiple Striders:
- Each Strider runs its Steps linearly.
- Steps can trigger jumps to other Striders via their Operations.
- The Flow continues until there are no more jumps.

This structure is **engine-agnostic**: it works inside any process engine, pipeline, or orchestration framework.  
It also fits naturally alongside:
- **Process Design Pattern (PDP)**: for process lifecycle control.
- **Stage Design Pattern (SDP)**: for event-based communication.

---

## ✅ When to use Strider Flows

- To make complex workflows modular, predictable, and testable.
- To break logic into clear, linear segments.
- To reuse common Steps or Striders across different Flows.

---

## 📄 License

MIT — free to use, modify, and extend.

---

**Author:** [Rafa Rodriguez](https://rafageist.com)
