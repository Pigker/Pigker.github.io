---
title: Serial-structured bipedal robot
summary: Design and control a Bipedal Robot.
date: 2024-05-05 
authors:
  - admin
# tags:
#   - Second Brain
#   - Markdown
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com)'
---
## Overview

1. We needed to independently design a robot capable of walking without wheels. I decided to create a bipedal robot to simulate human walking.
2. I started by sketching the robot’s basic shape, then developed a CAD model and used 3D printing to fabricate one of the robot’s legs.
3. Using a Raspberry Pi, I tested basic code functionality and electronic wiring to ensure the system operated correctly.
4. I then assembled the full robot and programmed it to perform simple walking movements, conducting initial gait tests.
5. I used MuJoCo as the simulation platform and created a custom simulation environment based on the gymnasium library. Meanwhile, I utilized the PPO algorithm from stable_baselines3 to train the model, enhancing the bipedal robot's walking ability by continuously modifying the reward function.

{{< youtube PUF_r42KNEg >}}

5. I iteratively upgraded the robot’s mechanical structure, increasing each leg’s degrees of freedom to improve its walking ability. Initially, I applied the hill-climbing algorithm to find motor control parameters for stable walking, but since control relied on sine functions, this approach had limitations.

{{< youtube 8UWeWlO6ypI >}}

6. I then implemented reinforcement learning to identify optimal actions to maximize walking speed. Due to the high computational demand and long training times, I only found some suboptimal actions. 
7. Here is a video of the complete process for the project.

{{< youtube CLA4x7UixoA >}}


<!-- ## Mindmaps

Hugo Blox supports a Markdown extension for mindmaps.

With this open format, can even edit your mindmaps in other popular tools such as Obsidian.

Simply insert a Markdown code block labelled as `markmap` and optionally set the height of the mindmap as shown in the example below.

Mindmaps can be created by simply writing the items as a Markdown list within the `markmap` code block, indenting each item to create as many sub-levels as you need:

<div class="highlight">
<pre class="chroma">
<code>
```markmap {height="200px"}
- Hugo Modules
  - Hugo Blox
  - blox-plugins-netlify
  - blox-plugins-netlify-cms
  - blox-plugins-reveal
```
</code>
</pre>
</div>

renders as

```markmap {height="200px"}
- Hugo Modules
  - Hugo Blox
  - blox-plugins-netlify
  - blox-plugins-netlify-cms
  - blox-plugins-reveal
```

Anh here's a more advanced mindmap with formatting, code blocks, and math:

<div class="highlight">
<pre class="chroma">
<code>
```markmap
- Mindmaps
  - Links
    - [Hugo Blox Docs](https://docs.hugoblox.com/)
    - [Discord Community](https://discord.gg/z8wNYzb)
    - [GitHub](https://github.com/HugoBlox/hugo-blox-builder)
  - Features
    - Markdown formatting
    - **inline** ~~text~~ *styles*
    - multiline
      text
    - `inline code`
    -
      ```js
      console.log('hello');
      console.log('code block');
      ```
    - Math: $x = {-b \pm \sqrt{b^2-4ac} \over 2a}$
```
</code>
</pre>
</div>

renders as

```markmap
- Mindmaps
  - Links
    - [Hugo Blox Docs](https://docs.hugoblox.com/)
    - [Discord Community](https://discord.gg/z8wNYzb)
    - [GitHub](https://github.com/HugoBlox/hugo-blox-builder)
  - Features
    - Markdown formatting
    - **inline** ~~text~~ *styles*
    - multiline
      text
    - `inline code`
    -
      ```js
      console.log('hello');
      console.log('code block');
      ```
    - Math: $x = {-b \pm \sqrt{b^2-4ac} \over 2a}$
```

## Highlighting

<mark>Highlight</mark> important text with `mark`:

```html
<mark>Highlighted text</mark>
```

## Callouts

Use [callouts](https://docs.hugoblox.com/reference/markdown/#callouts) (aka _asides_, _hints_, or _alerts_) to draw attention to notes, tips, and warnings.

By wrapping a paragraph in `{{%/* callout note */%}} ... {{%/* /callout */%}}`, it will render as an aside.

```markdown
{{%/* callout note */%}}
A Markdown aside is useful for displaying notices, hints, or definitions to your readers.
{{%/* /callout */%}}
```

renders as

{{% callout note %}}
A Markdown aside is useful for displaying notices, hints, or definitions to your readers.
{{% /callout %}}

Or use the `warning` callout type so your readers don't miss critical details:

{{% callout warning %}}
A Markdown aside is useful for displaying notices, hints, or definitions to your readers.
{{% /callout %}}

## Did you find this page helpful? Consider sharing it 🙌 -->
