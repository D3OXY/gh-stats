> **Note**
> This Repo Was Originally Created By [Anurag Hazra](https://github.com/anuraghazra).
> This is just a fork for private use.

<p align="center">
 <img width="100px" src="https://res.cloudinary.com/anuraghazra/image/upload/v1594908242/logo_ccswme.svg" align="center" alt="GitHub Readme Stats" />

<h2 align="center">GitHub Readme Stats</h2>
 <p align="center">Get dynamically generated GitHub stats on your READMEs!</p>

# Features

- [GitHub Stats Card](#github-stats-card)
- [GitHub Extra Pins](#github-extra-pins)
- [Top Languages Card](#top-languages-card)
- [Wakatime Week Stats](#wakatime-week-stats)
- [Themes](#themes)
  - [Responsive Card Theme](#responsive-card-theme)
- [Customization](#customization)
  - [Common Options](#common-options)
  - [Stats Card Exclusive Options](#stats-card-exclusive-options)
  - [Repo Card Exclusive Options](#repo-card-exclusive-options)
  - [Language Card Exclusive Options](#language-card-exclusive-options)
  - [Wakatime Card Exclusive Option](#wakatime-card-exclusive-options)
- [Deploy Yourself](#deploy-on-your-own)
  - [On Vercel](#on-vercel)
  - [On other platforms](#on-other-platforms)
  - [Keep your fork up to date](#keep-your-fork-up-to-date)

# GitHub Stats Card

Copy-paste this into your markdown content, and that is it. Simple!

Change the `?username=` value to your GitHub username.

```md
[![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy)](https://deoxy.dev)
```

> **Note**
> Available ranks are S+ (top 1%), S (top 25%), A++ (top 45%), A+ (top 60%), and B+ (everyone). The values are calculated by using the [cumulative distribution function](https://en.wikipedia.org/wiki/Cumulative_distribution_function) using commits, contributions, issues, stars, pull requests, followers, and owned repositories. The implementation can be investigated at [src/calculateRank.js](./src/calculateRank.js).

### Hiding individual stats

You can pass a query parameter `&hide=` to hide any specific stats with comma-separated values.

> Options: `&hide=stars,commits,prs,issues,contribs`

```md
![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&hide=contribs,prs)
```

### Adding private contributions count to total commits count

You can add the count of all your private contributions to the total commits count by using the query parameter `&count_private=true`.

> **Note**
> If you are deploying this project yourself, the private contributions will be counted by default. If you are using the public Vercel instance, you need to choose to [share your private contributions](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/managing-contribution-settings-on-your-profile/showing-your-private-contributions-and-achievements-on-your-profile).

> Options: `&count_private=true`

```md
![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&count_private=true)
```

### Showing icons

To enable icons, you can pass `&show_icons=true` in the query param, like so:

```md
![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true)
```

### Themes

With inbuilt themes, you can customize the look of the card without doing any [manual customization](#customization).

Use `&theme=THEME_NAME` parameter like so :

```md
![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=radical)
```

#### All inbuilt themes

GitHub readme stats comes with several built-in themes (e.g. `dark`, `radical`, `merko`, `gruvbox`, `tokyonight`, `onedark`, `cobalt`, `synthwave`, `highcontrast`, `dracula`).

<img src="https://res.cloudinary.com/anuraghazra/image/upload/v1595174536/grs-themes_l4ynja.png" alt="GitHub Readme Stats Themes" width="600px"/>

You can look at a preview for [all available themes](./themes/README.md) or checkout the [theme config file](./themes/index.js) & **you can also contribute new themes** if you like :D

#### Responsive Card Theme

[![Ishan's GitHub stats-Dark](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=dark#gh-dark-mode-only)](https://github.com/d3oxy/gh-stats#gh-dark-mode-only)
[![Ishan's GitHub stats-Light](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=default#gh-light-mode-only)](https://github.com/d3oxy/gh-stats#gh-light-mode-only)

Since GitHub will re-upload the cards and serve them from their [CDN](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-anonymized-urls), we can not infer the browser/GitHub theme on the server side. There are, however, four methods you can use to create dynamics themes on the client side.

##### Use the transparent theme

We have included a `transparent` theme that has a transparent background. This theme is optimized to look good on GitHub's dark and light default themes. You can enable this theme using the `&theme=transparent` parameter like so:

```md
![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=transparent)
```

<details>
<summary>:eyes: Show example</summary>

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=transparent)

</details>

##### Add transparent alpha channel to a themes bg_color

You can use the `bg_color` parameter to make any of [the available themes](./themes/README.md) transparent. This is done by setting the `bg_color` to a colour with a transparent alpha channel (i.e. `bg_color=00000000`):

```md
![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&bg_color=00000000)
```

<details>
<summary>:eyes: Show example</summary>

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&bg_color=00000000)

</details>

##### Use GitHub's theme context tag

You can use [GitHub's theme context](https://github.blog/changelog/2021-11-24-specify-theme-context-for-images-in-markdown/) tags to switch the theme based on the user GitHub theme automatically. This is done by appending `#gh-dark-mode-only` or `#gh-light-mode-only` to the end of an image URL. This tag will define whether the image specified in the markdown is only shown to viewers using a light or a dark GitHub theme:

```md
[![Ishan's GitHub stats-Dark](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=dark#gh-dark-mode-only)](https://github.com/d3oxy/gh-stats#gh-dark-mode-only)
[![Ishan's GitHub stats-Light](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=default#gh-light-mode-only)](https://github.com/d3oxy/gh-stats#gh-light-mode-only)
```

<details>
<summary>:eyes: Show example</summary>

[![Ishan's GitHub stats-Dark](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=dark#gh-dark-mode-only)](https://github.com/d3oxy/gh-stats#gh-dark-mode-only)
[![Ishan's GitHub stats-Light](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=default#gh-light-mode-only)](https://github.com/d3oxy/gh-stats#gh-light-mode-only)

</details>

##### Use GitHub's new media feature

You can use [GitHub's new media feature](https://github.blog/changelog/2022-05-19-specify-theme-context-for-images-in-markdown-beta/) in HTML to specify whether to display images for light or dark themes. This is done using the HTML `<picture>` element in combination with the `prefers-color-scheme` media feature.

```html
<picture>
<source 
  srcset="https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=dark"
  media="(prefers-color-scheme: dark)"
/>
<source
  srcset="https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true"
  media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
/>
<img src="https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true" />
</picture>
```

<details>
<summary>:eyes: Show example</summary>

<picture>
<source 
  srcset="https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=dark"
  media="(prefers-color-scheme: dark)"
/>
<source
  srcset="https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true"
  media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
/>
<img src="https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true" />
</picture>

</details>

### Customization

You can customize the appearance of your `Stats Card` or `Repo Card` however you wish with URL parameters.

#### Common Options

- `title_color` - Card's title color _(hex color)_. Default: `2f80ed`.
- `text_color` - Body text color _(hex color)_. Default: `434d58`.
- `icon_color` - Icons color if available _(hex color)_. Default: `4c71f2`.
- `border_color` - Card's border color _(hex color)_. Default: `e4e2e2` (Does not apply when `hide_border` is enabled).
- `bg_color` - Card's background color _(hex color)_ **or** a gradient in the form of _angle,start,end_. Default: `fffefe`
- `hide_border` - Hides the card's border _(boolean)_. Default: `false`
- `theme` - name of the theme, choose from [all available themes](./themes/README.md). Default: `default` theme.
- `cache_seconds` - set the cache header manually _(min: 14400, max: 86400)_. Default: `14400 seconds (4 hours)`.
- `locale` - set the language in the card _(e.g. cn, de, es, etc.)_. Default: `en`.
- `border_radius` - Corner rounding on the card. Default: `4.5`.

##### Gradient in bg_color

You can provide multiple comma-separated values in the bg_color option to render a gradient with the following format:

&bg_color=DEG,COLOR1,COLOR2,COLOR3...COLOR10

#### Stats Card Exclusive Options

- `hide` - Hides the [specified items](#hiding-individual-stats) from stats _(Comma-separated values)_. Default: `[] (blank array)`.
- `hide_title` - _(boolean)_. Default: `false`.
- `card_width` - Set the card's width manually _(number)_. Default: `500px  (approx.)`.
- `hide_rank` - _(boolean)_ hides the rank and automatically resizes the card width. Default: `false`.
- `show_icons` - _(boolean)_. Default: `false`.
- `include_all_commits` - Count total commits instead of just the current year commits _(boolean)_. Default: `false`.
- `count_private` - Count private commits _(boolean)_. Default: `false`.
- `line_height` - Sets the line height between text _(number)_. Default: `25`.
- `exclude_repo` - Exclude stars from specified repositories _(Comma-separated values)_. Default: `[] (blank array)`.
- `custom_title` - Sets a custom title for the card. Default:  `<username> GitHub Stats`.
- `text_bold` - Use bold text _(boolean)_. Default: `true`.
- `disable_animations` - Disables all animations in the card _(boolean)_. Default: `false`.
- `ring_color` - Color of the rank circle _(hex color)_. Defaults to the theme ring color if it exists and otherwise the title color.

> **Note**
> When hide_rank=`true`, the minimum card width is 270 px + the title length and padding.

#### Repo Card Exclusive Options

- `show_owner` - Show the repo's owner name _(boolean)_. Default: `false`.

#### Language Card Exclusive Options

- `hide` - Hide the languages specified from the card _(Comma-separated values)_. Default: `[] (blank array)`.
- `hide_title` - _(boolean)_. Default: `false`.
- `layout` - Switch between two available layouts `default` & `compact`. Default: `default`.
- `card_width` - Set the card's width manually _(number)_. Default `300`.
- `langs_count` - Show more languages on the card, between 1-10 _(number)_. Default `5`.
- `exclude_repo` - Exclude specified repositories _(Comma-separated values)_. Default: `[] (blank array)`.
- `custom_title` - Sets a custom title for the card _(string)_. Default `Most Used Languages`.
- `disable_animations` - Disables all animations in the card _(boolean)_. Default: `false`.
- `hide_progress` - It uses the compact layout option, hides percentages, and removes the bars. Default: `false`.

> **Warning**
> Language names should be URI-escaped, as specified in [Percent Encoding](https://en.wikipedia.org/wiki/Percent-encoding)
> (i.e: `c++` should become `c%2B%2B`, `jupyter notebook` should become `jupyter%20notebook`, etc.) You can use
> [urlencoder.org](https://www.urlencoder.org/) to help you do this automatically.

#### Wakatime Card Exclusive Options

- `hide` - Hide the languages specified from the card _(Comma-separated values)_. Default: `[] (blank array)`.
- `hide_title` - _(boolean)_. Default `false`.
- `line_height` - Sets the line height between text _(number)_. Default `25`.
- `hide_progress` - Hides the progress bar and percentage _(boolean)_. Default `false`.
- `custom_title` - Sets a custom title for the card _(string)_. Default `Wakatime Stats`.
- `layout` - Switch between two available layouts `default` & `compact`.  Default `default`.
- `langs_count` - Limit the number of languages on the card, defaults to all reported languages _(number)_.
- `api_domain` - Set a custom API domain for the card, e.g. to use services like [Hakatime](https://github.com/mujx/hakatime) or [Wakapi](https://github.com/muety/wakapi) _(string)_. Default `Waka API`.
- `range` – Request a range different from your WakaTime default, e.g. `last_7_days`. See [WakaTime API docs](https://wakatime.com/developers#stats) for a list of available options. _(YYYY-MM, last_7_days, last_30_days, last_6_months, last_year, or all_time)_. Default `all_time`.

---

# GitHub Extra Pins

GitHub extra pins allow you to pin more than six repositories in your profile using a GitHub readme profile.

Yay! You are no longer limited to 6 pinned repositories.

### Usage

Copy-paste this code into your readme and change the links.

Endpoint: `api/pin?username=d3oxy&repo=github-readme-stats`

```md
[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=d3oxy&repo=github-readme-stats)](https://deoxy.dev)
```

### Demo

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=d3oxy&repo=github-readme-stats)](https://deoxy.dev)

Use [show_owner](#customization) variable to include the repo's owner username

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=d3oxy&repo=github-readme-stats&show_owner=true)](https://deoxy.dev)

# Top Languages Card

The top languages card shows a GitHub user's most frequently used top language.

> **Note**
> Top Languages does not indicate my skill level or anything like that; it's a GitHub metric to determine which languages have the most code on GitHub. It is a new feature of github-readme-stats.

### Usage

Copy-paste this code into your readme and change the links.

Endpoint: `api/top-langs?username=d3oxy`

```md
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=d3oxy)](https://deoxy.dev)
```

### Exclude individual repositories

You can use the `&exclude_repo=repo1,repo2` parameter to exclude individual repositories.

```md
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=d3oxy&exclude_repo=github-readme-stats,anuraghazra.github.io)](https://deoxy.dev)
```

### Hide individual languages

You can use `&hide=language1,language2` parameter to hide individual languages.

```md
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=d3oxy&hide=javascript,html)](https://deoxy.dev)
```

### Show more languages

You can use the `&langs_count=` option to increase or decrease the number of languages shown on the card. Valid values are integers between 1 and 10 (inclusive), and the default is 5.

```md
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=d3oxy&langs_count=8)](https://deoxy.dev)
```

### Compact Language Card Layout

You can use the `&layout=compact` option to change the card design.

```md
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=d3oxy&layout=compact)](https://deoxy.dev)
```

### Hide Progress Bars

You can use the `&hide_progress=true` option to hide the percentages and the progress bars (layout will be automatically set to `compact`).

```md
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=d3oxy&hide_progress=true)](https://deoxy.dev)
```

### Demo

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=d3oxy)](https://deoxy.dev)

- Compact layout

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=d3oxy&layout=compact)](https://deoxy.dev)

- Hidden progress bars

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=d3oxy&hide_progress=true)](https://deoxy.dev)

# Wakatime Week Stats

Change the `?username=` value to your [Wakatime](https://wakatime.com) username.

```md
[![Ishan's wakatime stats](https://github-readme-stats.vercel.app/api/wakatime?username=D3OXY)](https://deoxy.dev)
```

> **Note**:
> Please be aware that we currently only show data from Wakatime profiles that are public.

### Demo

[![Ishan's wakatime stats](https://github-readme-stats.vercel.app/api/wakatime?username=D3OXY)](https://deoxy.dev)

[![Ishan's wakatime stats](https://github-readme-stats.vercel.app/api/wakatime?username=D3OXY&hide_progress=true)](https://deoxy.dev)

- Compact layout

[![Ishan's wakatime stats](https://github-readme-stats.vercel.app/api/wakatime?username=D3OXY&layout=compact)](https://deoxy.dev)

---

### All Demos

- Default

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy)

- Hiding specific stats

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&hide=contribs,issues)3
- Showing icons

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&hide=issues&show_icons=true)

- Customize Border Color

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&border_color=2e4058)

- Include All Commits

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&include_all_commits=true)

- Themes

Choose from any of the [default themes](#themes)

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&show_icons=true&theme=radical)

- Gradient

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api?username=d3oxy&bg_color=30,e96443,904e95&title_color=fff&text_color=fff)

- Customizing stats card

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api/?username=d3oxy&show_icons=true&title_color=fff&icon_color=79ff97&text_color=9f9f9f&bg_color=151515)

- Setting card locale

![Ishan's GitHub stats](https://github-readme-stats.vercel.app/api/?username=d3oxy&locale=es)

- Customizing repo card

![Customized Card](https://github-readme-stats.vercel.app/api/pin?username=d3oxy&repo=github-readme-stats&title_color=fff&icon_color=f9f9f9&text_color=9f9f9f&bg_color=151515)

- Top languages

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=d3oxy)](https://deoxy.dev)

- WakaTime card

[![Ishan's wakatime stats](https://github-readme-stats.vercel.app/api/wakatime?username=D3OXY)](https://deoxy.dev)

---

### Quick Tip (Align The Repo Cards)

By default, GitHub does not lay out the cards side by side. To do that, you can use this approach:

```html
<a href="https://github.com/d3oxy/gh-stats">
  <img align="center" src="https://github-readme-stats.vercel.app/api/pin/?username=d3oxy&repo=github-readme-stats" />
</a>
<a href="https://github.com/anuraghazra/convoychat">
  <img align="center" src="https://github-readme-stats.vercel.app/api/pin/?username=d3oxy&repo=convoychat" />
</a>
```

## :sparkling_heart: Support the project

Support the Original [Creator](https://github.com/anuraghazra) of this project by giving a :star: on the project and sharing it with your friends via social media.
[Anurag Hazra](https://github.com/anuraghazra)

Thanks! :heart:

---

[![https://vercel.com?utm_source=github_readme_stats_team&utm_campaign=oss](./powered-by-vercel.svg)](https://vercel.com?utm_source=github_readme_stats_team&utm_campaign=oss)

Contributions are welcome! &lt;3

Made with :heart: and JavaScript.

