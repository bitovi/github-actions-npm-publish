

# Increment and publish NPM

The action will increment the version, save the updated version back to GitHub, createing a tag of the new version, and optionally publish the NPM package to NPM.

### Inputs

The following inputs can be used as `step.with` keys

| Name      | Type       | Req. | Description                                                  |
| --------- | ---------- | ---- | ------------------------------------------------------------ |
| update_ type      | String     | Yes  | Should be `major`, `minor`, or `patch`                       |
| publish   | true/false | No   | Defaults to `true`.  Set to false to update version without publishing |
| npm_token | String     | Yes  | NPM token that has publish permissions                       |


# Example

This will checkout the code, and publish to NPM


```yaml
      - name: Checkout
        uses: actions/checkout@v2

      - name: Use Node.js
        uses: actions/setup-node@v2
        with:
          node-version: "16"

      - name: "Install"
        run: npm ci

      - name: "Increment and publish"
        uses: bitovi/github-actions-npm-publish:v1.0.0
        with:
          update_type: 'patch'
          npm_token: ${{ secrets.NPM_TOKEN }}
          publish: true
            
```

## Contributing
We would love for you to contribute to [`bitovi/github-actions-deploy-eks-helm`](https://github.com/bitovi/github-actions-deploy-eks-helm).   [Issues](https://github.com/bitovi/github-actions-deploy-eks-helm/issues) and [Pull Requests](https://github.com/bitovi/github-actions-deploy-eks-helm/pulls) are welcome!

## License
The scripts and documentation in this project are released under the [MIT License](https://github.com/bitovi/github-actions-deploy-eks-helm/blob/main/LICENSE).

## Provided by Bitovi
[Bitovi](https://www.bitovi.com/) is a proud supporter of Open Source software.

## Need help or have questions?
You can **get help or ask questions** on [Discord channel](https://discord.gg/J7ejFsZnJ4)! Come hangout with us!

Or, you can hire us for training, consulting, or development. [Set up a free consultation](https://www.bitovi.com/devops-consulting).
