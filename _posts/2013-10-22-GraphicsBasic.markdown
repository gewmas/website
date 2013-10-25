---
layout: post
title:  "Graphics Basic"
date:   2013-10-22 12:47:00
categories: Graphics
---
<ul id="menu">
	<li><span>&#x25bc;</span><b>Graphics Basic</b>
	<ul>
		<li><h2>Pixel</h2></li>
			<p>
				1 bit grayscale</br>
				8 bit RGB (24 bits/pixel)</br>
				16 bit RBG (48 bits/pixel)</br>
			</p>
		
		<li><h2>2D transformations</h2></li>
			<p>
				Translation</br>
				<img src="../../../../asset/graphics/translation.png"></br>
				Scaling</br>
				<img src="../../../../asset/graphics/scaling.png"></br>
				Rotation about z-axis</br>
				<img src="../../../../asset/graphics/rotationAboutZ.png"></br>
				Rotation about x-axis</br>
				<img src="../../../../asset/graphics/rotationAboutX.png"></br>
				Rotation about y-axis</br>
				<img src="../../../../asset/graphics/rotationAboutY.png"></br>
				Rotation about point</br>
				<img src="../../../../asset/graphics/rotationAboutPoint.png"></br>
				Rotation about axis</br>
				{% highlight c++ %}
				glRotatef(angle, 0, 0, 1); // z axis
				glRotatef(angle, 0.707, 0.707, 0);
				{% endhighlight %}
				<img src="../../../../asset/graphics/rotationAboutVector1.png"></br>
				<img src="../../../../asset/graphics/rotationAboutVector2.png"></br>
			</p>
	</ul>
	</li>

	<li><span>&#x25b6;</span><b>OpenGL Drawing</b>
	<p>
		Basic OpenGL function:
		{% highlight c++ %}
		void glColor3f(GLfloat red, GLfloat green, GLfloat blue);
		void glRotatef(GLdouble angle, GLdouble x, GLdouble y, GLdouble z); 
		/*mode - GL POINTS, GL LINES,GL LINE STRIP, GL LINE LOOP GL TRIANGLES, GL TRIANGLE STRIP,
		GL TRIANGLE FAN, GL QUADS, GL QUAD STRIP, and GL POLYGON*/
		void glBegin(GLenum mode); glEnd();
		{% endhighlight %}
	</p>
	<p>
		<script src="https://gist.github.com/myhgew/5f82ed47097eb06baa91.js"></script>
	</p>
	</li>

	<li><span>&#x25b6;</span><b>Shading</b>
	<ul>
		<li>Diffuse</li>
		<p> Energy from light source depends on angle to light source. </br>
			Max illumination - surface directly toward light source. </br>
			Min illumination - surfacetangent to light source. </br>
			L_d = k_d * I * max(0, n {dot product} l) </br>
		</p>
		<li>Specular</li>
		<p>
			Reflection brightest when v and i are symmetric across surface normal. </br>
			h = bisector(v, l) </br>
			L_s = k_s * I * max(0, n {dot product} h)^p </br>
		</p>
		<li>Ambient</li>
		<p>
			Independent of everything, add constant color, fill in black shadow. </br>
			L_a = k_a * I_a </br>
		</p>
	</ul>
	</li>
	<li>
	<span>&#x25b6;</span><h1>Perspective and Viewing</h1>
	<ul id="menu">
		<li>Orthographic Projection</li>
		<ul>
			<li>Mechanical and architectural drawings</li>
			<li>Parallel lines are parallel!</li>
			<li>Preserve size and shape</li>
		</ul>
		<p>
			ray direction -> -w </br>
			ray origin(s) -> e + uu+ vv
		</p>
		<li>Perspective Projection</li>
		<ul>
			<li>Pass through a single point</li>
			<li>Not parallel to each other</li>
			<li>Not perpendicular to image plane</li>
		</ul>
		<p>
			ray direction -> e + uu + vv - dw </br>
			ray origin(s) -> e
		</p>
		<li>Pixel to image map</li>
		<p>
			u = l + (r-l)(i+0.5)/n_x </br>
			v = b + (t-b)(j+0.5)/n_y </br>
		</p>
		<li>OrthoNormal camera frame</li>
		<ul>
			<li>u, v, w</li>
			<li>right-handed</li>
			<li>v up!</li>
			<li>view-direction -w</li>
		</ul>
	</ul>
	</li>
	<span>&#x25b6;</span><li><h1>Texture Mapping</h1></li>
	<p>
		A technique of defining surface properties (expecially shading parameters) in such a way that they vary as a function of position on the surface. </br>
		A general technique for storing and evaluating functions.
	</p>
	<span>&#x25b6;</span><li><h1>Sampling and Reconstruction</h1></li>
	<p>
		Convolution, (a*b)[i] = SIMGA(j) a[j]b[i-j]
	</p>
	<h1>Filter</h1>
	<ul>
		<li>Box filter</li>
		<li>Tent filter</li>
		<li>Gaussian filter</li>
		<li>B-Spline cubic</li>
		<li>Catmull-Rom cubic</li>
	</ul>
	<h1>Near the edge</h1>
	<ul>
		<li>clip filter(black)</li>
		<li>wrap around</li>
		<li>copy edge</li>
		<li>reflect across edge</li>
		<li>vary filter near edge</li>
	</ul>
	<span>&#x25b6;</span><li><h1>Ray Tracing</h1></li>
	<p>
		{% highlight java %}
		for(each pixel){
		compute viewing ray
		intersect ray with scene
		compute illumination at visbile point
		put result into image
	}
	{% endhighlight %}
</p>
<span>&#x25b6;</span><li><h1>Line Drawing</h1></li>
<p>
	{% highlight c++ %}
	//y = b + mx;
	x = ceil(x0);
	y = round(m*x+b);
	d = m*(x+1)+b-y;
	while(x == floor(xl))
	{
	if(d > 0.5){
	y += 1;
	d -= 1;
}
x += 1;
d += m;
output(x, y);
}
{% endhighlight %}
</p>
</li>
</ul>

<div id="reference">
	<h1>Reference</h1>
	<p>
		<a href='http://www.crcpress.com/product/isbn/9781568814698'>Fundamentals of Computer Graphics</a>
	</p>
</div>