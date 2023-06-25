# Sassy Mixins

## Never write a `_mixins.scss` file again.

You've finally realized you should respect the preferences of users on the web. (You were probably told to, though.) Either way, it's about time.

This criminally lightweight package grants you the power to use the latest media query features from the [Media Queries Level 5 CSS specification](https://www.w3.org/TR/mediaqueries-5/) to ensure you build web experiences that respect settings and preferences a user has selected in their browser or their operating system.

## Available mixins (9)

### Color (4)
- Forced colors
- Inverted colors
- Contrast: more
- Contrast: less

### Data (1)
- Reduced data

### Motion (1)
- Reduced motion

### Theme (2)
- Dark mode
- Light mode (non-dark mode)

### Transparency (1)
- Reduced transparency

## How to use this package

Assuming you're using [Sass](https://sass-lang.com) already, you have two easy steps:

1. Install the package as a development dependency.

```sh
npm install -D sassy-mixins
```

2. Reference `sassy-mixins/index.scss` in your Sass file and use the mixins. (I recommend namespacing your import so you know which place your mixins come from, but it's not required.)

```scss
@use '{path/to/your/node_modules}/sassy-mixins/mixins' as sassy;

.dubstep-lighting {
  animation: pulsate 500ms infinite;

  @include sassy.prefers-reduced-motion {
    animation: none;
  }
}
```

**Note:** The path to the location of the `sassy-mixins/_mixins.scss` file may change depending on your project configuration or code bundlers you are using. You should probably use a relative path.

### @use vs. @import

- If you use Dart Sass **>= v1.23.0**, you can use `@use`.
- If you use LibSass or Ruby Sass, you **must** use `@import`.


## Frequently asked questions

### Will this increase my bundle size?
No. [Sass partials are not compiled into CSS](https://sass-lang.com/guide#topic-4).

The code contained in `_mixins.scss` is not directly compiled into CSS.

### Will this make me a better developer?
Yes. Not only does respecting user preferences make you a better developer, it makes you a better human being.

### Can I use this with LESS?
Sure. You can copy the code inside the `@mixin` and replace the `@content` with whatever code you want to apply for that user preference.

### Can I use this without Sass?
Sure. You can copy the code inside the `@mixin` and replace the `@content` with whatever code you want to apply for that user preference.


## Future additions

Whenever the Media Queries specification publishes a new draft, I will update this package.