# Netlify dev CLI windows zombie processes demo

> This issue ONLY affects Windows. POSIX systems seem ok.

## Reproduction:

### Baseline (proving it's a netlify cli problem)
* Ensure you have no `node.exe` processes running
* Run `npm run dev` on Windows
* You should see two `node.exe` processes, for `npm` and `tsc` respectively
* Type ctrl-c. There will no longer be any `node.exe` processes.

### The problem
* Ensure you have no `node.exe` processes running
* Run `npx netlify dev` on Windows
* You should see 3-4 `node.exe` processes, for `netlify`, `npm` and `tsc` respectively
* Type ctrl-c. There will still be two `node.exe` processes (`npm` and `tsc`) that are now zombies and must be manually terminated