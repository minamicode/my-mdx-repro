# Bug Reproduction: MDX metadata export broken with webpack in Next.js 16.2.0

## Description

`export const metadata` from an MDX page fails to build in Next.js 16.2.0 when using webpack. The same code works fine in 16.1.6 and also works in 16.2.0 with Turbopack.

This pattern is explicitly documented as supported: https://nextjs.org/docs/app/guides/mdx

## Steps to Reproduce

1. Clone this repo
2. Run `npm install`
3. Run `npm run build` (uses `--webpack` flag)
4. Build fails with: `You are attempting to export "metadata" from a component marked with "use client"`

## Expected Behavior

Build succeeds as documented and as it did in 16.1.6.

## Actual Behavior

Build fails with webpack. Works fine with Turbopack.

## Versions

- next: 16.2.0 (broken) / 16.1.6 (working)
- @next/mdx: 16.2.0
- Bundler: webpack (broken) / Turbopack (works)
