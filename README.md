



# Example
```
      - name: Checkout
        uses: actions/checkout@v2

      - name: Use Node.js
        uses: actions/setup-node@v2
        with:
          node-version: "16"

      - name: "Install"
        run: npm ci

      - name: "Increment and publish"
        uses: bitovi/github-actions-npm-publish:main
            

```