# Compatibility Actions


## Examples

### Development
The development workflow will run the workflow on every push to a branch that is not the main branch. It will create a new release that is promoted to a channel with the same name as the branch.
The next job will setup a compatibility matrix of clusters, deploy the app and execute some tests. Once everything is successful the created clusters and customers will be removed again.
Based on your preference you can either use the simplified smoke-test version, or the highly customizable version.

#### Smoke Test
See the [example workflow](example-workflows/development-helm-smoke-test.yaml) for more details and also the [smoke-test](smoke-test) directory for the actual action.

https://github.com/replicatedhq/compatibility-actions/blob/749a205e6ed9031d7781e33a5f5764b1982bbef8/example-workflows/development-helm-smoke-test.yaml#L1-L54

#### Customizable

##### Installation with Helm
See the [example workflow](example-workflows/development-helm.yaml) for more details.

https://github.com/replicatedhq/compatibility-actions/blob/749a205e6ed9031d7781e33a5f5764b1982bbef8/example-workflows/development-helm.yaml#L1-L140

##### Installation with KOTS
See the [example workflow](example-workflows/development-kots.yaml) for more details.

https://github.com/replicatedhq/compatibility-actions/blob/749a205e6ed9031d7781e33a5f5764b1982bbef8/example-workflows/development-kots.yaml#L1-L133

### Releasing
The releasing workflow will run the workflow each time a tag is being placed on the repository. It will create a new release that is promoted to a channel with the same name as the tag.
The next job will setup a compatibility matrix of clusters, deploy the app and execute some tests. Once everything is successful the release will be promoted to the stable channel. And the created clusters and customers for the compatibility matrix will be removed again.

See the [example workflow](example-workflows/release.yaml) for more details.

https://github.com/replicatedhq/compatibility-actions/blob/749a205e6ed9031d7781e33a5f5764b1982bbef8/example-workflows/release.yaml#L1-L151