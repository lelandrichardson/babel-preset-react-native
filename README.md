# babel-preset-react-native

This package is copied from [RN Core](https://github.com/facebook/react-native/tree/master/babel-preset).

Hot Module Reloading offers an extremely improved developer experience, but does not typically work
with `React.PureComponent`. If you use this preset instead of the real one, and also switch out `React.PureComponent` with `React.Component` only when `module.hot` is true, then HMR can work with
pure components. This affects performance, but allows for HMR to
work on all components in our codebase, which is a net win. In order to do this, however, we need
to tell `react-transform` to run on `PureComponent` as well. Although this *is* a configuration
option, the way the plugin is used inside of metro-bundler does not allow for us to pass in this
configuration option. As a result, we are duplicating this here and resolving the module to this
file path instead.
