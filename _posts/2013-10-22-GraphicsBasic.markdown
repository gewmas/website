---
layout: post
title:  "Graphics Basic"
date:   2013-10-22 12:47:00
categories: Graphics
---
<ol>
	<li>
		<h1>Graphics Basic</h1>
		<ul>
			<li>
				<h2>Pixel</h2>
				<p>
					1 bit grayscale</br>
					8 bit RGB (24 bits/pixel)</br>
					16 bit RBG (48 bits/pixel)</br>
				</p>
			</li>
			<li>
				<h2>2D transformations</h2>
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
			</li>
		</ul>
	</li>
	<li>
		<h1>OpenGL Drawing</h1>
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
	<li>
		<h1>Shading</h1>
		<p>
		</p>
	</li>
	<li>
		<h1>Viewing</h1>
		<p>
		</p>
	</li>
	<li>
		<h1>Texture Mapping</h1>
		<p>
		</p>
	</li>
	<li>
		<h1>Sampling and Reconstruction</h1>
		<p>
		</p>
	</li>
	<li>
		<h1>Ray Tracing</h1>
		<p>
		</p>
	</li>
	<li>
		<h1>Line Drawing</h1>
		<p>
		</p>
	</li>
</ol>

<div id="reference">
	<h1>Reference</h1>
	<p>
		<a href='http://www.crcpress.com/product/isbn/9781568814698'>Fundamentals of Computer Graphics</a>
	</p>
</div>