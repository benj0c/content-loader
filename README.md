# Angular Content Loader

[![All Contributors](https://img.shields.io/badge/all_contributors-11-orange.svg?style=flat-square)](#contributors-)

<p align="center">
  <img width="400" alt="Example's react-content-loader" src="https://user-images.githubusercontent.com/4838076/34308760-ec55df82-e735-11e7-843b-2e311fa7b7d0.gif" />
</p>

Angular component that uses SVG to create a collection of loaders which simulates the structure of the
content that will be loaded, similar to Facebook cards loaders.

[Live Demo](https://stackblitz.com/edit/ngx-content-loader)

## Sponsoring ngneat

[Sponsorships](https://github.com/sponsors/ngneat) aid in the continued development and maintenance of ngneat libraries. Consider asking your company to sponsor ngneat as its core to their business and application development.

### Gold Sponsors

Elevate your support by becoming a Gold Sponsor and have your logo prominently featured on our README in the top 5 repositories.

### Silver Sponsors

Boost your backing by becoming a Gold Sponsor and enjoy the spotlight with your logo prominently showcased in the top 3 repositories on our README.

### Bronze Sponsors

<a href="https://houseofangular.io" target="_blank">
  <img src="https://github.com/ngrx/platform/blob/main/projects/ngrx.io/src/assets/images/sponsors/house-of-angular.png" width="50px" height="50px" alt="House of Angular" />
</a>

Become a bronze sponsor and get your logo on our README on GitHub.

## Features

This is an Angular port for [react-content-loader](https://github.com/danilowoz/react-content-loader).

- :gear: **Completely customizable:** you can change the colors, speed and sizes;
- :pencil2: **Create your own loading:** use the
  [create-react-content-loader](https://danilowoz.github.io/create-react-content-loader/) to create
  your custom loadings easily;
- :ok_hand: **You can use right now:** there are a lot of presets to use the loader, see the
  [options](#examples);
- :rocket: **Performance:** uses pure SVG to work, so it works without any extra scripts,
  canvas, etc;

<a href="https://www.buymeacoffee.com/basalnetanel" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

## Install

### Yarn

```bash
yarn add @ngneat/content-loader
```

## Usage

```ts
import { ContentLoaderModule } from '@ngneat/content-loader';

@NgModule({
  imports: [ContentLoaderModule]
})
export class AppModule {}
```

```html
<content-loader>
  <svg:rect x="0" y="0" rx="3" ry="3" width="250" height="10" />
  <svg:rect x="20" y="20" rx="3" ry="3" width="220" height="10" />
  <svg:rect x="20" y="40" rx="3" ry="3" width="170" height="10" />
  <svg:rect x="0" y="60" rx="3" ry="3" width="250" height="10" />
  <svg:rect x="20" y="80" rx="3" ry="3" width="200" height="10" />
  <svg:rect x="20" y="100" rx="3" ry="3" width="80" height="10" />
</content-loader>
```

> Warning: Safari renders the SVG in black in case your Angular application uses the `<base href="/" />` tag in the `<head/>` of your `index.html`.
> Refer to the input property `baseUrl` below to fix this issue.

### Examples

#### Facebook Style

```html
<facebook-content-loader></facebook-content-loader>
```

![Facebook Style](https://user-images.githubusercontent.com/4838076/34308760-ec55df82-e735-11e7-843b-2e311fa7b7d0.gif)

#### List Style

```html
<list-content-loader></list-content-loader>
```

![List Style](https://user-images.githubusercontent.com/4838076/36352948-b8931430-149e-11e8-9f4b-3f00bc444a6d.gif)

#### Bullet list Style

```html
<bullet-list-content-loader></bullet-list-content-loader>
```

![Bullet list Style](https://user-images.githubusercontent.com/4838076/31998372-59817bac-b96e-11e7-8ef8-07f61670ee18.gif)

## API

### @Inputs

| <div style="width:250px">Prop name and type</div>           | Environment | Description                                                                                                                                                                                                                                                                                         |
| ----------------------------------------------------------- | ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **`animate?: boolean`** <br/> Defaults to `true`            | -           | Opt-out of animations with `false`                                                                                                                                                                                                                                                                  |
| **`baseUrl?: string`**<br /> Defaults to an empty string    | -           | Required if you're using `<base url="/" />` document `<head/>`. <br/>This prop is common used as: <br/>`<ContentLoader baseUrl={window.location.pathname} />` which will fill the SVG attribute with the relative path. Related [#93](https://github.com/danilowoz/react-content-loader/issues/93). |
| **`speed?: number`** <br /> Defaults to `1.2`               | -           | Animation speed in seconds.                                                                                                                                                                                                                                                                         |
| **`interval?: number`** <br /> Defaults to `0.25`           | -           | Interval of time between runs of the animation, <br/>as a fraction of the animation speed.                                                                                                                                                                                                          |
| **`viewBox?: string`** <br /> Defaults to `undefined`       | -           | Use viewBox props to set a custom viewBox value, <br/>for more information about how to use it, <br/>read the article [How to Scale SVG](https://css-tricks.com/scale-svg/).                                                                                                                        |
| **`gradientRatio?: number`** <br /> Defaults to `1.2`       | -           | Width of the animated gradient as a fraction of the view box width.                                                                                                                                                                                                                                 |
| **`rtl?: boolean`** <br /> Defaults to `false`              | -           | Content right-to-left.                                                                                                                                                                                                                                                                              |
| **`backgroundColor?: string`** <br /> Defaults to `#f5f6f7` | -           | Used as background of animation.                                                                                                                                                                                                                                                                    |
| **`foregroundColor?: string`** <br /> Defaults to `#eee`    | -           | Used as the foreground of animation.                                                                                                                                                                                                                                                                |
| **`backgroundOpacity?: number`** <br /> Defaults to `1`     | -           | Background opacity (0 = transparent, 1 = opaque)<br/>used to solve an issue in [Safari](#safari--ios)                                                                                                                                                                                               |
| **`foregroundOpacity?: number`** <br /> Defaults to `1`     | -           | Animation opacity (0 = transparent, 1 = opaque)<br/>used to solve an issue in [Safari](#safari--ios)                                                                                                                                                                                                |
| **`style?: CSSProperties`** <br /> Defaults to `{}`         | -           |                                                                                                                                                                                                                                                                                                     |

## Credits

This is basically an Angular port for [react-content-loader](https://github.com/danilowoz/react-content-loader).

## License

MIT &copy; [NetanelBasal](https://github.com/NetanelBasal)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://www.netbasal.com"><img src="https://avatars1.githubusercontent.com/u/6745730?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Netanel Basal</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=NetanelBasal" title="Code">💻</a> <a href="#content-NetanelBasal" title="Content">🖋</a> <a href="https://github.com/NetanelBasal/content-loader/commits?author=NetanelBasal" title="Documentation">📖</a></td>
    <td align="center"><a href="https://www.mapianist.com"><img src="https://avatars0.githubusercontent.com/u/7777929?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Heo</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=leo6104" title="Code">💻</a></td>
    <td align="center"><a href="http://www.andreas.ae"><img src="https://avatars3.githubusercontent.com/u/2174826?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Andreas Aeschlimann</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=andreas-aeschlimann" title="Documentation">📖</a></td>
    <td align="center"><a href="https://github.com/alexw10"><img src="https://avatars0.githubusercontent.com/u/9453636?v=4?s=100" width="100px;" alt=""/><br /><sub><b>alexw10</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=alexw10" title="Code">💻</a> <a href="https://github.com/NetanelBasal/content-loader/commits?author=alexw10" title="Documentation">📖</a></td>
    <td align="center"><a href="https://github.com/nonsocode"><img src="https://avatars3.githubusercontent.com/u/12021370?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Chinonso Chukwuogor</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=nonsocode" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/wynfred"><img src="https://avatars2.githubusercontent.com/u/9249564?v=4?s=100" width="100px;" alt=""/><br /><sub><b>wynfred</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=wynfred" title="Code">💻</a></td>
    <td align="center"><a href="https://twitter.com/irustm"><img src="https://avatars1.githubusercontent.com/u/16316579?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Rustam</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=irustm" title="Code">💻</a></td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/gund"><img src="https://avatars0.githubusercontent.com/u/3644678?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Alex Malkevich</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=gund" title="Documentation">📖</a></td>
    <td align="center"><a href="https://github.com/danielsogl"><img src="https://avatars2.githubusercontent.com/u/15234844?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Daniel Sogl</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=danielsogl" title="Code">💻</a> <a href="#maintenance-danielsogl" title="Maintenance">🚧</a> <a href="#platform-danielsogl" title="Packaging/porting to new platform">📦</a></td>
    <td align="center"><a href="http://www.tailored.hu/"><img src="https://avatars1.githubusercontent.com/u/9606801?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Alex Szabó‮</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=kreatemore" title="Code">💻</a></td>
    <td align="center"><a href="http://codepen.io/donroyco/"><img src="https://avatars2.githubusercontent.com/u/1763537?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Roy</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=donroyco" title="Documentation">📖</a></td>
    <td align="center"><a href="https://robinvdb.me/"><img src="https://avatars2.githubusercontent.com/u/3083785?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Robin Van den Broeck</b></sub></a><br /><a href="https://github.com/NetanelBasal/content-loader/commits?author=RobinVdBroeck" title="Code">💻</a></td>
  </tr>
</table>

<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
