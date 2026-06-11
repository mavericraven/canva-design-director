# Canva MCP Workflows

**1. Generative Initiation**
- Use `generate-design-structured` for controlled layouts rather than generic text prompts.

**2. The Editing Transaction (Crucial)**
- `start-editing-transaction` > obtain `transaction_id`.
- `perform-editing-operations` > Apply strict X/Y coordinate adjustments, exact font sizing, and color hex assignments.
- Verify via `get-design-thumbnail` if possible.
- `commit-editing-transaction` to save, or `cancel-editing-transaction` if the layout is structurally compromised.

**3. Resizing (Pro Feature)**
- Use `resize-design` to adapt master creatives to social specs, then initiate an editing transaction to re-balance the layout for the new aspect ratio.
