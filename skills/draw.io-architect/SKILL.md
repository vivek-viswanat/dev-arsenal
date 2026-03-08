---
name: Draw.io Architect
description: Expert in generating and modifying editable .drawio architecture diagrams.
---

# When to use
Use this skill when the user asks to "visualize the architecture," "draw a flow," or "create a system diagram."

# Instructions
1. **Format:** Always output diagrams in the `mxfile` XML format used by draw.io.
2. **Naming:** Save files with the `.drawio` extension.
3. **Styling:** Use the theme defined in `config/default-style.json`. Default to 'Rounded' rectangles and 'Orthogonal' connectors.
4. **Icons:** Refer to `references/aws-icons.md` if the user mentions cloud infrastructure.
5. **Updating:** If a `.drawio` file already exists, read the XML and modify only the necessary `mxCell` elements rather than regenerating from scratch.

# Example
User: "Draw a diagram of a web app with a React frontend and a FastAPI backend."
Agent: [Generates valid <mxfile> XML and saves it to architecture.drawio]