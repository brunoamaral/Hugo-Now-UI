---
title: "Elements"
date: 2018-11-15T22:26:15+01:00
draft: false
resources:
    - src: images/IMG_0160.JPG
      name: header
    - src: "gallery/*.jpg"
      name: gallery-:counter
      title: gallery-title-:counter
      
    - src: carousel/slide1.jpg
      name: slide
      title: slide 1 
    - src: carousel/slide2.jpg
      name: slide 
      title: slide 2  
    - src: carousel/slide3.jpg
      name: slide 
      title: slide 3 
options:
  unlisted: true
  showHeader: true
---


<h2 class="title">Full Width Image</h2>


```md

{{%/* image-fullwidth src="images/IMG_0160.JPG" class="" */%}}

```



{{% image-fullwidth src="images/IMG_0160.JPG" class="" %}}

<h2 class="title">Image float left </h2>

```md

{{%/* image-floatleft src="https://placekitten.com/200/300" class="animate left" */%}}

```
{{% image-floatleft src="https://placekitten.com/200/300" class="animate left" %}}Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repudiandae illum nesciunt magnam explicabo iure ipsum quae accusamus esse, laboriosam nulla tenetur debitis facere natus cupiditate, rem officia quis, odit cumque. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Impedit assumenda iure aspernatur dolor doloremque delectus voluptas, libero illo, quo. Nostrum, tenetur, amet! Consequatur dolorem quam provident a eaque, doloribus aut!


<div class="clearfix"></div>

<h2 class="title">Image float right </h2>

```md 

{{%/* image-floatright src="https://placekitten.com/200/300" class="animate right" */%}}

```

{{% image-floatright src="https://placekitten.com/200/300" class="animate right" %}}Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repudiandae illum nesciunt magnam explicabo iure ipsum quae accusamus esse, laboriosam nulla tenetur debitis facere natus cupiditate, rem officia quis, odit cumque. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Impedit assumenda iure aspernatur dolor doloremque delectus voluptas, libero illo, quo. Nostrum, tenetur, amet! Consequatur dolorem quam provident a eaque, doloribus aut!

<div class="clearfix"></div>

<h2 class="title">Side by side images</h2>

```md

{{%/* image-sidebyside src="images/TunisTea-11_11.jpg" class="animate left" */%}}

{{%/* image-sidebyside src="images/TunisTea-2_11.jpg" class="animate left" */%}}

```



{{% image-sidebyside src="images/TunisTea-11_11.jpg" class="animate left" %}}

{{% image-sidebyside src="images/TunisTea-2_11.jpg" class="animate right" %}}


<div class="clearfix"></div>
<h2 class="title">Panorama</h2>

```md

{{</* panorama type="equirectangular" image="31138750083_5e3bfa7df6_o.jpg" showControls="true" autoload="true" author="Benjamim" autorotate="1" */>}}

```



{{< panorama type="equirectangular" image="/post/creating-a-360-photo-viewer/31138750083_5e3bfa7df6_o.jpg" showControls="true" autoload="true" author="Benjamim" autorotate="1" >}}

<h2 class="title">Gallery</h2>


```md

{{%/* gallery folder="gallery" title="Jameson at Spark 2018" */%}}

```

{{% gallery folder="gallery" title="Jameson at Spark 2018" %}}

<h2 class="title">Carousel</h2>

```md
{{%/* carousel title="optional" */%}}
```

{{% carousel title="round and round it goes" %}}

