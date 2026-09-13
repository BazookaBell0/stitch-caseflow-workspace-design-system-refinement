# Caseflow Worker Design System

## Authority

The existing HTML and PNG screen pairs in this repository are the **canonical visual and interaction reference** for Caseflow Worker.

When generating a new implementation, preserve those screens with high visual fidelity. Change the implementation technology, not the product design.

Do not reinterpret Caseflow into a generic SaaS dashboard. Do not simplify supported screens because another component shape is easier to code.

If this document and an existing approved screen appear to differ visually, the approved screen artifact wins unless a later explicit Human-approved design change says otherwise.

## Visual language

Caseflow is calm, focused, warm, tactile, and mobile-first.

### Color tokens

- Canvas: `#F9F9F7`
- Recessed surface: `#F4F4F2`
- Grouped surface: `#EEEEEC`
- Elevated surface: `#FFFFFF`
- Carbon / primary text: `#161616`
- Secondary text: `#5F6160`
- Tertiary text: `#858784`
- Divider: `#E8E8E5`
- Primary clay: `#9A442D`
- Soft clay: `#FFDAD2`

Do not substitute approximate beige/brown/rust values.

## Typography

Primary typeface: **Plus Jakarta Sans**.

Use a system sans fallback only when necessary in implementation.

Typical hierarchy:
- screen/client titles: 28–30px, extra-bold;
- sheet/workflow titles: 20–24px, bold/extra-bold;
- section headings: 16–18px, bold;
- body/list content: 15–16px;
- text-entry controls on mobile: 16px;
- metadata/navigation labels: about 12–14px with sufficient contrast.

Do not replace Plus Jakarta Sans with Inter as the final Caseflow visual language.

## Layout and shape

- Mobile-first, primarily designed around approximately 390–420px phone widths.
- Must remain usable at approximately 320px without horizontal overflow.
- Phone gutters are approximately 20px.
- Important touch targets are at least 44px, usually 48–50px.
- Use rounded tactile cards, grouped stacks, pill actions, floating dock navigation, and bottom-sheet interactions exactly where shown in approved screens.
- Use subtle dividers and light shadows; avoid heavy borders around every surface.
- Keep desktop constrained and readable rather than stretching content edge-to-edge.

## Canonical interaction patterns

### Client Overview
Preserve the approved hierarchy shown by the existing Client Overview artifact:
1. compact client/context header;
2. Current;
3. Open commitments;
4. Recent;
5. floating bottom navigation.

Quick Capture is not a permanently expanded engineering form on Client Overview. It is a dedicated Capture interaction.

### Capture
Use the approved dedicated Capture sheet/surface with client context, note entry, and explicit Save.

Current MVP behavior is online-only: successful Save means the server confirmed persistence.

### Edit Current
Use the approved bottom-sheet interaction rather than expanding the normal Current card into a large inline form.

### Tasks / commitments
Use grouped, scannable rows and the dedicated client task views shown in this repository. Preserve due-state hierarchy and task-detail interactions.

### Recent
Use the dedicated contextual Recent screens and grouped activity rows shown in this repository.

### Privacy Review
Use a focused privacy-review surface. Protected text is visually central. Example placeholders in the mocks are illustrative; production data must come from the actual privacy pipeline.

### Program selection / switching
Preserve the simple stacked program choice and bottom-sheet switching patterns shown by the approved artifacts.

## Accessibility

- semantic headings and landmarks;
- real buttons and form controls;
- visible keyboard focus;
- 44px+ important touch targets;
- readable contrast;
- no meaning conveyed through color alone;
- large text/zoom must not clip core actions;
- sheet/modal focus behavior should be accessible.

## Implementation translation rule

The original Stitch HTML may use Tailwind CDN, Google Fonts CDN, Material Symbols, or standalone HTML. Those are prototype implementation details, not the production stack.

Reproduce the visual result using Caseflow's real React/TypeScript/Vite stack and application-owned CSS. Do **not** copy prototype runtime dependencies wholesale merely to match the screen.
