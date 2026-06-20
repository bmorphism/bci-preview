# bci.place preview — stable redirect front

Stable front for the (ephemeral) Forester preview host of `plurigrid/place` PRs.

- **Stable base:** https://bmorphism.github.io/bci-preview/
- Any path is preserved and redirected to the live host listed in [`target.txt`](./target.txt).
- The PRs (#25, #30) link here, so the links survive preview-host churn.

## When the preview host changes
Update **one file** and push:

```bash
echo "https://files-morphvm-<newid>.http.cloud.morph.so" > target.txt
git commit -am "point at new preview host" && git push
```

`404.html`/`index.html` fetch `target.txt` client-side, so no HTML edits are needed.
