# Next.js 15 App Router Bug: Missing Return in Function Component

This repository demonstrates a bug encountered in Next.js 15's App Router when using a function component that lacks a return statement.  The expected behavior would be a clear error indicating the missing return, however, the actual behavior is unexpected and may lead to difficult-to-debug issues.

## Bug Description
In Next.js 15's App Router, a function component in a page without an explicit `return` statement does not throw a clear, descriptive error. Instead, it might produce unexpected rendering behavior, such as rendering nothing or rendering previous content, making the error difficult to pinpoint.

## How to Reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm run dev` to start the Next.js development server.
4. Observe the rendered output.  The page should display an error message.

## Solution
The solution is straightforward: ensure all functional components in your Next.js 15 App Router have an explicit return statement, even if the component renders nothing.  You may use null or an empty div:

```javascript
export default function Home() {
  return null; // or <></>
}
```
