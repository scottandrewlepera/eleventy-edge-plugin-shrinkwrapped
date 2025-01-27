# Eleventy Edge Plugin Shrinkwrapped

A shrinkwrapped copy of the original Eleventy Edge plugin.

## Wait, what?

The [original Eleventy Edge plugin](https://www.11ty.dev/docs/plugins/edge/) enabled easy integrations with Netlify Edge Functions. This plugin was [removed](https://www.11ty.dev/docs/plugins/edge/) from the Eleventy bundle with v3.0 and is no longer an official plugin.

At the time of this writing, the original plugin code was not easily available. This repo contains a drop-in "shrinkwrapped" copy of the code.

Please note:

- This plugin is currently unmaintained (as was the original)
- Tested with Eleventy 3.0.0.
- Compatibility with newer versions is not guaranteed.

## How do I use it?

1. Install the Netlify CLI (if you haven't already)
1. Download the [latest ZIP or tarball](./tags) and decompress it
2. copy the `11ty-edge` folder to your Eleventy folder
3. Add the plugin to your `.eleventy.js` configuration:

```
const EleventyEdgePlugin = require("./11ty-edge/");

module.exports = function(eleventyConfig) {
  eleventyConfig.addPlugin(EleventyEdgePlugin); 
};
```

5. Run `netlify dev`. This will create an `eleventy-edge` edge function.
6. Assign routes to the edge function in your `netlify.toml` file.

```
[[edge_functions]]
  function = "eleventy-edge"
  path = "/some/route/"
```

See the [original documentation](https://v2.11ty.dev/docs/plugins/edge/) on how to use the plugin to create dynamic content.

## Why did you do this?

There are other ways to integrate with Edge Functions, but being able to drop in the original code was a quick way to get it.

Also, I'm lazy.

## Why haven't you published this to NPM?

I'm lazy.

Scott Andrew LePera, 2025-01-26<br />
[scottandrew.com](https://scottandrew.com)<br />
hire.scott@airpost.net
