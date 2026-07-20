# Mathieu Sync Notes

Flow for syncing with `urob/main` while keeping the Corne branch controlled:

1. Merge `urob/main` into `updated_urob_main`.
2. Open a PR from `updated_urob_main` to `main` to review the upstream urob changes.
3. Create or update `update_corne_with_updated_urob_main` from `corne`.
4. Merge `updated_urob_main` into `update_corne_with_updated_urob_main`.
5. Review the differences that need to be carried from the shared base files into the Corne-specific files.

Files to compare carefully:

- `config/base.keymap` -> `config/corne_base.keymap`
- `config/combos.dtsi` -> `config/corne_combos.dtsi`
- Any shared config or helper usage that affects Corne builds

Keep Corne hardware-specific choices in the Corne files, especially the `build.yaml` board target:

```yaml
board: nice_nano@2.0.0//zmk
```
