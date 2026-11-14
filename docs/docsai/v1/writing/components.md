# Use reader components

Reader components turn plain Markdown into callouts, numbered steps, tabs, link cards and collapsible questions. Insert them with the **Blocks** toolbar in the visual editor or the **Insert block** toolbar in Markdown source.

## Callout

Use a callout for something the reader must not miss. Types: `info` (Note), `warning` (Warning), `error` (Danger) and `success` (Tip).

<Callout type="warning" title="Keep it private">

Never paste a token, a password or customer data into a page.

</Callout>

## Steps

Use steps for a procedure. Each step starts with a heading.

<Steps>

<Step>

## Start a branch

Choose **Start editing**.

</Step>

<Step>

## Commit

Choose **Commit source changes**.

</Step>

</Steps>

## Tabs

Use tabs for alternatives, such as the same command in two shells. Tabs with the same `groupId` switch together, and `persist="true"` remembers the reader's choice.

<Tabs groupId="shell" persist="true">

<TabItem value="bash" label="Bash">

```bash
git switch -c work/author/components-page
```

</TabItem>

<TabItem value="powershell" label="PowerShell">

```powershell
git switch -c work/author/components-page
```

</TabItem>

</Tabs>

## Cards

Use cards for *Next steps* and for choosing a path. Each card links to a site route or an `https` URL.

<Cards>
<Card title="Create a page" href="/docs/docsai/v1/create-a-page/" description="Start a branch and use New page." />
<Card title="Submit for review" href="/docs/docsai/v1/submit-for-review/" description="Commit and submit the exact commit." />
</Cards>

## Accordions

Use accordions for questions and answers, so readers scan the questions first.

<Accordions type="single">
<Accordion title="Do components work in Markdown source?">

Yes. Both modes edit the same file.

</Accordion>
<Accordion title="Can I put a component inside another?">

A callout can hold cards, and a step or an accordion can hold a callout, tabs or a code block.

</Accordion>
</Accordions>

## Code blocks with a title

Add `title="..."` after the language to show a file name above a code block.

```json title="catalog.json"
{"schemaVersion": 2}
```
