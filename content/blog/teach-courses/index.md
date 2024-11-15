---
title: AutoURDF Unsupervised Robot Modeling from Point Cloud Frames Using Cluster Registration
summary: Train a model that can generate a URDF file from a video of a robot's point cloud.
date: 2024-11-07
math: true
authors:
  - admin
# tags:
#   - Hugo
#   - Hugo Blox Builder
#   - Markdown
image:
  caption: 'Embed rich media such as videos and LaTeX math'
---
## Overview

1. An experimental platform is designed to study the robotic arm's motion range and camera field of view, using the camera to capture point cloud data of the robotic arm.

2. Each frame of point cloud data is segmented using the k-means algorithm, dividing it into multiple segments. 

3. A multi-layer perceptron (MLP) model is then trained on these segments, using Chamfer distance as the loss function to compute the transformation matrix for each segment. A distance matrix is calculated to determine the relative distance between pairs of points, aiding in coordinate partitioning during the clustering process.

4. Before generating the URDF file, we classify the robotic arm's links into two cases: known and unknown degrees of freedom (DOF). For known DOF, links are directly divided; for unknown DOF, we use the silhouette score method to search for the optimal DOF within a specified range. This method increments the DOF value, clustering at each step and calculating silhouette scores to select the DOF with the best clustering quality.

5. Using the NetworkX library, a graph structure is created to represent the connections between links. The minimum spanning tree (MST) method is employed to establish the primary link connections, resulting in an acyclic, connected kinematic tree. Based on the segmentation results, a URDF file and corresponding kinematic tree are generated, facilitating the modeling and visualization of the robotic arm's structure.


In this project, I was primarily responsible for the design and setup of the experimental platform, data collection, partial process optimization, and implementation of some code.



<!-- [Hugo Blox Builder](https://hugoblox.com) is designed to give technical content creators a seamless experience. You can focus on the content and the Hugo Blox Builder which this template is built upon handles the rest.

**Embed videos, podcasts, code, LaTeX math, and even test students!**

On this page, you'll find some examples of the types of technical content that can be rendered with Hugo Blox.

## Video

Teach your course by sharing videos with your students. Choose from one of the following approaches:

**Youtube**:

    {{</* youtube D2vj0WcvH5c */>}}

{{< youtube D2vj0WcvH5c >}}

**Bilibili**:

    {{</* bilibili BV1WV4y1r7DF */>}}

{{< bilibili BV1WV4y1r7DF >}}

**Video file**

Videos may be added to a page by either placing them in your `assets/media/` media library or in your [page's folder](https://gohugo.io/content-management/page-bundles/), and then embedding them with the _video_ shortcode:

    {{</* video src="my_video.mp4" controls="yes" */>}}

## Podcast

You can add a podcast or music to a page by placing the MP3 file in the page's folder or the media library folder and then embedding the audio on your page with the _audio_ shortcode:

    {{</* audio src="ambient-piano.mp3" */>}}

Try it out:

{{< audio src="ambient-piano.mp3" >}}

## Test students

Provide a simple yet fun self-assessment by revealing the solutions to challenges with the `spoiler` shortcode:

```markdown
{{</* spoiler text="👉 Click to view the solution" */>}}
You found me!
{{</* /spoiler */>}}
```

renders as

{{< spoiler text="👉 Click to view the solution" >}} You found me 🎉 {{< /spoiler >}}

## Math

Hugo Blox Builder supports a Markdown extension for $\LaTeX$ math. Enable math by setting the `math: true` option in your page's front matter, or enable math for your entire site by toggling math in your `config/_default/params.yaml` file:

```yaml
features:
  math:
    enable: true
```

To render _inline_ or _block_ math, wrap your LaTeX math with `$...$` or `$$...$$`, respectively.

Example **math block**:

```latex
$$
\gamma_{n} = \frac{ \left | \left (\mathbf x_{n} - \mathbf x_{n-1} \right )^T \left [\nabla F (\mathbf x_{n}) - \nabla F (\mathbf x_{n-1}) \right ] \right |}{\left \|\nabla F(\mathbf{x}_{n}) - \nabla F(\mathbf{x}_{n-1}) \right \|^2}
$$
```

renders as

$$\gamma_{n} = \frac{ \left | \left (\mathbf x_{n} - \mathbf x_{n-1} \right )^T \left [\nabla F (\mathbf x_{n}) - \nabla F (\mathbf x_{n-1}) \right ] \right |}{\left \|\nabla F(\mathbf{x}_{n}) - \nabla F(\mathbf{x}_{n-1}) \right \|^2}$$

Example **inline math** `$\nabla F(\mathbf{x}_{n})$` renders as $\nabla F(\mathbf{x}_{n})$.

Example **multi-line math** using the math linebreak (`\\`):

```latex
$$f(k;p_{0}^{*}) = \begin{cases}p_{0}^{*} & \text{if }k=1, \\
1-p_{0}^{*} & \text{if }k=0.\end{cases}$$
```

renders as

$$
f(k;p_{0}^{*}) = \begin{cases}p_{0}^{*} & \text{if }k=1, \\
1-p_{0}^{*} & \text{if }k=0.\end{cases}
$$

## Code

Hugo Blox Builder utilises Hugo's Markdown extension for highlighting code syntax. The code theme can be selected in the `config/_default/params.yaml` file.


    ```python
    import pandas as pd
    data = pd.read_csv("data.csv")
    data.head()
    ```

renders as

```python
import pandas as pd
data = pd.read_csv("data.csv")
data.head()
```

## Inline Images

```go
{{</* icon name="python" */>}} Python
```

renders as

{{< icon name="python" >}} Python

## Did you find this page helpful? Consider sharing it 🙌 -->
