- [PNPM Cleaning and Resetting](#pnpm-cleaning-and-resetting)
  - [One-liner](#one-liner)
- [**Steps for Clean Reset Using `pnpm`**](#steps-for-clean-reset-using-pnpm)
- [Why `--force`?](#why---force)
- [Key Use Cases for `--force`](#key-use-cases-for---force)

### PNPM Cleaning and Resetting

#### One-liner

```bash
find . -name node_modules -type d | grep -v pnpm | xargs rm -rf && rm pnpm-lock.yaml && pnpm store prune && pnpm install --force
```

To do a **clean reset** on a repo using `pnpm`, you generally want to remove installed dependencies, clear any generated files, and then reinstall them from scratch. Here's how to achieve that clean reset:

---

### **Steps for Clean Reset Using `pnpm`**

1. **Delete `node_modules` and `pnpm-lock.yaml`**
   This removes installed dependencies and any lock files that `pnpm` uses.

```bash
pnpm remove node_modules
rm pnpm-lock.yaml
```

Alternatively:

```bash
pnpm store prune
pnpm install --force
```

2. **Clear cache (if you want a fresh cache)**  
   `pnpm` caches packages globally, but sometimes clearing the cache can help avoid issues.

```bash
pnpm store prune
```

### Why `--force`?

The `--force` option in `pnpm install --force` forces `pnpm` to:

1. **Rebuild all dependencies:**  
   It will ignore any cached versions of the dependencies and rebuild everything from scratch, even if the current versions are already installed in `node_modules`.

2. **Ignore lockfile optimization:**  
   `pnpm` typically skips reinstalling dependencies if it detects that the lockfile (`pnpm-lock.yaml`) hasn’t changed, but with `--force`, it bypasses this optimization and installs everything again.

### Key Use Cases for `--force`

- When you suspect corrupted or outdated dependencies.
- When you’ve made changes to the lockfile or dependencies manually.
- When builds are failing due to improper dependency resolution or stale artifacts.

In essence, `pnpm install --force` is like doing a **hard reset** for dependencies, ensuring everything is fresh and fully rebuilt.
