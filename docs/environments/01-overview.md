---
id: overview
title: Overview
---

A Bit environment is a development environment encapsulated in a single Bit component. An environment includes linting, testing, compiling, documenting, and other [services](/environments/environment-services) which are needed in the lifecycle of an independent component.

Having just a single component to set up the entire development environment means no time gets wasted on tedious configurations. In addition, a sharable environment makes it easier to maintain consistency in development across multiple decoupled Bit workspaces.

A single workspace may also use multiple environments to "service" different groups of components. This gives us the freedom to author, maintain and explore different types of components, all in the same workspace.

For example, the following configuration sets two different environments, [React](/react/overview) and [Node](/nodejs/overview), on two groups of components, selected by their directories, `components/ui` and `components/utils`.

```json
{
  "teambit.workspace/variants": {
      "components/ui": {
        "teambit.react/react": {}
      },
      "components/utils": {
        "teambit.harmony/node"
      }
  }
}
```

Bit provides [a number of environments to choose from](/environments/choose-an-environment). Each environment is completely [customizable and extendible](/environments/build-environment). Once you've created your own custom environment, you can share it with others, as you would with any other Bit component.

## Environments CLI reference

As mentioned above, Bit environments make use of Bit's CLI to execute their different services. That means, `bbit test`, for example, may execute different test runners, depending on the environment in use.

### Run the Dev Server

```shell
bbit start
```

### Run the build pipeline

```shell
bbit build
```

- [Learn more](/build-pipeline/overview).

### Run all tests

```shell
bbit test
```

- [Learn more](/testing/overview).

### Compile all components

```
bbit compile
```

- [Learn more](/compiling/overview).

### Get lint results

```
bbit lint
```