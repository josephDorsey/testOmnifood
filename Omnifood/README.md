# testOmnifood

Following along with a Udemy HTML and CSS course will use this as a framework to help build other websites

# 1. Define your project

Start off by defining the goal of your project. This can be showing your portfolio to the world, selling an e-book, building a blog, etc.
Also define your audience. Ask yourself: which is the typical user that will visit my website?
This is important, because you should always design with your goal and audience in mind.

2. Plan out everything

Once your project is defined, plan your content carefully. This includes text, images, videos, icons, etc.
Remember what I told you about visual hierarchy. It plays an important role when you start thinking about what you want on your website and what you don't. Defining the content before actually starting the design is called the content-first approach. It means that you should design for the content, instead of designing a webpage and then filling it with some stuff.
Define the navigation.
Define the site structure. You can draw a sitemap in this step if we're talking about a bigger project.

3. Sketch your ideas before you design

Now it's time to get inspired and think about your design.
Then, get the ideas out of your head. And with that I mean that you should sketch your ideas before you start designing. It will help you explore ideas and create a concept of what you want to build. Using pencil and paper is a great way of quickly retaining your valuable ideas.
Make as many sketches as you want, but don't spend too much time perfecting anything. Once you have an initial idea, you can concentrate on the details when designing in HTML and CSS.
I advise you to never, ever start designing without having an idea of what you want to build. Getting inspiration is very important in this phase, and I already told you how to do that!

4. Design and develop your website

After sketching, start to design your website using all the guidelines and tips you've learned in the web design section.
You'll do that using HTML and CSS, which is called designing in the browser. Designing in the browser is basically designing and developing at the same time.
There are more and more designers leaving traditional design programs such as Photoshop and start designing in the browser. The biggest reason for this is that you can't design responsive websites in photoshop. It also saves you tons of time.
In this phase, you'll use your sketches, content and planning decisions you've made in steps 1, 2 and 3.

5. It's not done yet: optimization

Before you can actually launch your beautiful masterpiece for the world to see it, we have to optimize its performance in terms of site speed.
You also need to do some basic search engine optimization (SEO) for search engines such as google.

6. Launch the masterpiece

Your optimized website is now finally ready to launch.
All you need for launching is a webserver that will host your website and deliver it to the world.

7. Site maintenance

The launch of your website is not the end of the story.
Now it's time to monitor your users' behavior and make some changes to your website if necessary.
You should also update your content regularly in order to show your users that your website is alive! For instance, a blog can be a great way of doing that.

# 2. Setting up the Fluid Grid 2/10/2021 7:09 PM

1.  There are Three Ingredients to Responsive Webdesign

    1.  Fluid grid: all layout elements are sized in relative unites, such as percentages, instead of absolute units like pixels
    2.  Flexible images: are also sized in relative unites
    3.  Media queries: allow us to specify different CSs style rules for different browser widths.

2.  Now we are gonna link the grid file
    <link rel="stylesheet" href="vendors/css/grid.css" />
3.  In the video he pans back to the responsivegridsystem.com website and tells us that most of our items are going to be in columns. And each of these groups of columns is a row

    1.  now for the responsive part, on that page if we resize it all of them shrink and that means that they are defined with a relative width and because their width is always relative to the browser window
    2.  and when they get too small they start to stick and they will collapse and become readable

4.  lets define the row (max width of the window is 1140px)
    row {
    max-width; 1140px;
    }
5.  How do we center all of the rows?

    1.  to center a container inside another container we set the left and right margin to auto

            margin: 0 auto 0 auto;

        this can be rewritten as
        margin: 0 auto; now top and bottom are 0 and left and right will be auto

# Section 5: Building Header Part #1 Notes 2/10/2021 7:06 PM

-this link does go anywhere, its a dummy link until you know where you want to reference your link
<a href="#"></a>

1. first we are going to add the background image to the header. Here the file the project wants us to use is called hero.jpg. Make sure the file is in the img folder of the css folder
   -how do we use this in CSS?
   background-image: url(img/hero.jpg);

2. What was wrong? The image only takes up a portion of the content thats on the page. We want to make it so the viewport will be as high as the page

   - if we set it to height: 100vh;
   - this means its showing 100% of the view port

   header {
   background-image: url("/resources/css/img/hero.jpg");
   height: 100vh;
   }

3. Whats wrong now? the white space from the h1
   -Use the inspect tool from the chrome dev tools
   -Now we find out that the h1 has a margin from the normalize.css lets find a way to get rid of this:

   - we give h1 a margin of 0 and now the white space is gone
     - h1 {
     - margin: 0;
     - }

4. So what's wrong now? The image is way too zoomed in, so we have to tell the browser in some way that we want to see the whole image
   -to do this we mess with the background-size
   and we set it to cover
   -have the background centered, so we used background-position: center;

   header {
   background-image: url("/resources/css/img/hero.jpg");
   background-size: cover;
   background-position: center;
   }

5. What happens now if we re-size the window?
   -it will always try to find a way to show us the whole image

6. So now lets try to find a way to center the h1 box
   1. How do we do this? this time we wont be using the responsive fluid grid that we set up before, because we want this box to be absolutely position. its the only way to we can horizontally and vertically center it
   2. so after we give it a position of absolute, a width of 1140px and top 50%, and left 50% to center it on the page.
      1. What is the issue now? it looks weird its too far over, how we do fix this?
      2. With TRANSFORM! transform(translate (-50%, -50%));
         1. so what this does it translates the element half of its width and of its height up and to the left
7. So what happens now? The text is centered as we want, it always stays in the middle BUT the contrast between the text and the image is way too low, its hard to see anything
   1. bad idea to just put text on the image
   2. lets make the image darker
   3. lets use a linear-gradient() on top of the image
      1. it takes in two colors 1. background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
         url("/resources/css/img/hero.jpg");
      1. we dont want complete black so we set it to 70% transparency

# Section 5: Building Header Part #2 Notes 2/10/2021 7:51 PM

1.  In this section we are gonna work on main heading and the two buttons
2.  lets make the main heading white
    1. now lets change our font size, since the html font size is 20px and we want this is a fluid responsive design we want everything to be relative, so if we say the font-size is 200% that means that our h1 element will be 40px; if we then want to change the font-size for the h1 all we would need to do is change the global font-size in the html and it will decrease the h1 as well
       1. we will use this type of method for all other elements on the webpage
       2. so it will all be defined relatively to this base size of 20px, then by adjusting this, all other elements will automatically adjust their size.
3.  When we use very big headlines we should decrease the font weight and set it to uppercase (cause usually the h1 elements come with bold formatting and thats not what we want)

    1. decrease the font weight to 300
    2. next we use text-transform to make it uppercase
    3. next we add letter-spacing and assign it 1px (so its not so compressed)
    4. next we add word-spacing and assign it 4px;

4.  Whats the issue now? We have this ugly line break here at healthy meals and we dont want that
    1. so lets just break it at 'Hello Super Healthy Meals'
    2. Do you remember how to do that?
       1. we use <br>
       2. much better!
       3.
5.  Now lets format these buttons here we want one button to be a full orange, and the other one to be a transparent ghost like button

    1.  we assign them both the btn class and another class that differentiates them like btn-full and btn-ghost

        1.  In the box-model lecture we were told about block elements and inline elements
            1. Now there is also a mix between those two elements, which is called the inline-block
               1. inline-block: is just like an inline element, but that can have heading and margin
               2. So the difference is that it doesnt force a line break but youy can attribute it some padding and some margin unlike a normal inline element
        2.  a is already and inline element, but we want it to be a inline-block

            1.  we can change that by using display: inline-block;
            2.  now lets add some padding we want the top to be 10px bottom 10 px right left 30px
            3.  Whats happening now? lets get rid of the blue under line with text-decoration

                1.  This is the common button setup

                            .btn {

                    display: inline-block;
                    padding: 10px 30px;
                    font-weight: 300;
                    text-decoration: none;
                    color: #fff;
                    }

# Section 5: Building Header Part #2 Notes (flatuicolors.com)

1.  So now lets start on the btn-full class and choose a color
2.  We will use Flat Ui tool (flatuicolors.com) 1. we will pick a color closet to the orange color we need 2. nest we copy the color we want and get the hex code value for it 1. Very good!
3.  Maybe now we want some border-radius here to add some rounded edges on both sizes 1. lets make it something crazy high, maybe 200px
4.  So now lets try to style the ghost button 1. we want the border to be orange 2. so we will make it a 1px solid #e67e22;

5.  Whats the issue now? Notice how one button is slightly larger than the other? 1. Theres a reason for that remember the Box-model? 1. the height and the width of an element is the content plus the padding plus the border 1. in order to make them into the same height and width we jsut add that border to the other button as well 2. and we want some space so lets add some margin to h1 1. in h1 we gave it a margin-top of 0 and margin-bottom of 20px

6.  So we defined how the buttons look like, now buttons or links in general can have different states:
    _We wamt the buttons to not have an appearance of being clicked on before or after so this is why we are styling them like the regular btn settings_

    1.  link = how the element looks in the normal state
        1. How do we specify? this? btn:link (makes a pseudo class) So this means the, a element in its normal state
    2.  visited = how the element looks after it has been visited
        1. How do we specify this? btn:visited
    3.  active = when we click on the button
    4.  hover = when we hover over the button with our mouse

    EXAMPLE
    .btn:link,
    .btn:visited,

    .btn-full:link,
    .btn-full:visited

    .btn-ghost:link,
    .btn-ghost:visited

# Section 5: Building Header Part #2 Notes (0to255 tool) Perfect for hover states, borders, gradients, and more

1.  We can specify that in CSS so we can say what will happen when we put the mouse on the button

    .btn:hover,
    .btn:active {

}

1.  For this we want hover and active to have an darker orange tone so that we can see some change there right?
2.  What tool do we use to get darker shades of color? (0to255);

go to 0to255 tool > enter the color you picked > there will be a wheel of shades for that color that go from lighest to darkest

1.  Now wwe give it a background color
    .btn:hover,
    .btn:active {
    background-color: #cf6d17;
    }
2.  So now our buttons when we hover over them they now have a darker shade
3.  What is our issue now? It's the text color and the border color
    1.  as you can see the lighter color orange is still seen when hovering over it
    2.  How do we fix? We want it to have the darker shade we just selected
        1. -first we will copy the .btn-full-link, .btn-full:visited, and .btn-ghost:link, bt-ghost:visited;
        2. to change what we want so we dont have to write everything again
        3. so .btn-full:hover,visited should not only have this background color here but the border should have the color too #cf6d17
        4. we want the same for .btn-ghost the only difference is that the font color chamges to white (#fff) to give it a nice shine when hovered over

EXAMPLE
.btn-full:hover,
.btn-full:active {
border: 1px solid #cf6d17;
}

        .btn-ghost:hover,
        .btn-ghost:active {
        border: 1px solid #cf6d17;
        color: #fff;
        }

4. Now one more thing this is a little more advanced, we want to have a transition from one color to another at this moment we dont get a nice transition from the ghost button to the ghost:hover orange color.
   1. How do we fix this?
      1. in the btn class we need a transition property
      2. so we set transition: background-color 0.2s - sets the background color to change in 0.2s
         1. we can also specify more than one property here
            1. transition: background-color 0.2s, border 0.2s, color 0.2s;
         2. We also want some margins between the buttons caused they are pretty glued together right now
            1. So we are going to change the full button and add a margin to the right
               1. So when i say 15px to the right we put margin-right: 15px;

# Section 5: Building Header Part #3 Notes

1. What are we missing here? We want the logo image in the top left and some navigation bar on the top right
2. Notice how the code is starting to get a little long? lets make a nice code structure here so that we organize everything into logical pieces of code
   1. we will use CSS comments like below
3. EXAMPLE

   /_ ---------------------------------------------- _/
   /_ BASIC SETUP _/
   /_ ---------------------------------------------- _/

4. EXAMPLE

/_ ---------------------------------------------- _/
/_ REUSABLE COMPONENTS _/
/_ ---------------------------------------------- _/

1. EXAMPLE
   /_ -------- HEADINGS --------- _/

1. EXAMPLE
   /_ -------- BUTTONS --------- _/

1. EXAMPLE

/_ ---------------------------------------------- _/
/_ HEADER _/
/_ ---------------------------------------------- _/

We want to seperate our code into categories like this

A. So now lets add a <nav></nav> element to the header above the <div class=" hero-text-box"></div> - we will call this <div class="row"> and if you remember this row that we specialized is going to center everything in the navigation
-the row will always be centered
-now we want the logo, so first lets put the logo inside of our folder
-lets take all the photos from the omnifood folder and put them in the resources > img folder
-they gave us two logo backgrounds but we want to use the white one because we have a dark background
-create an <img> element src and alt and class with the name of logo
-now lets do the navigation

1.  Navigation is usually in <ul class="main-nav"></ul>unordered lists, which is like some bullet points
2.  where each bullet point will be an element

    1.  <ul class="main-nav"></ul>
    2.  now we make a <li></li> which is like a listed element, now each of the list elements will be <a></a> link because thats what a navigation is all about right?

        1.  its like a collection of links
        2.  so lets check the page of things that they wanted
        3.  they wanted a nav section of 4 links with these items below:
            TURN THIS INTO LIST 1. Food delivery (Section 1) 2. How it works (Section 3) 3. Our cities (Section 4) 4. Sign up (Section 6)

                  <li><a href="#">Food Delivery</a></li>
                  <li><a href="#">How it works</a></li>
                  <li><a href="#">Our cities</a></li>
                  <li><a href="#">Sign up</a></li>

        4.  Whats the issue now? The logo image is too big and with the list you can see the bullet points and blue links how do we get rid of it?

Lets work on the .logo and .main-nav formatting

1. we are gonna give the logo a height of 100px, set the width to automatically adjust so auto, and we want the image to be on the left, so lets float left
2. with the main-nav we want it on the left side of the page so lets float it to the right
3. lets format the navigation in the way that almost everyone does it in
4. So the first thing here is in this unordered list because main nav is an unordered list, right, lets get rid of the bullet points
5. we assign <ul class="main-nav"></ul> a list-style: none;
6. next we target <li> and we want to target them all in the main-nav so we do
7. .main-nav li
8. again, we want to change the way they are displayed
9. originally they are block elements so lets make them inline-blocks so that they will be side by side and we want to add some margin between them
10. so each of the blocks will have a margin on the left side of 40px
11. so now the li elements are nicely aligned as we want them
12. now its time to format how the links inside of them look
13. in order to do that we can go further down and select .main-nav li a
14. we can give it a color of white and give it a text decoration of none to get rid of the underlines and lets make them uppercase
15. lets specify the font size, this shouldnt be too big because as you know our base font size is 20px and say we want it to be 18px, but we will NEVER use the unit in pixels, we want it to be 18 pixels but expressed in a percentage
16. So what do we do?
17. We want to divide that 18 pixels we want by this base (which is 20 in this EXAMPLE)
18. to do that we need to do 18px / 20 which gives us 0.9 which is 90%
19. Use command space bar to open spotlight and use as a calculator 1. So we will just say we want the font size to be 90 percent and now it will give us 18 pixels
20. Now we probably want some distance between the logo and the top and the center the navigation so it lines up with the logo
21. so now we will add some margin to the top of the logo with 20px
22. now we will add a margin-top of 55px to the .main-nav
23. now lets ad something when we hover on the li elements that it gives it a 2px border to the bottom
    .main-nav li a:link,
    .main-nav li a:visited {
    color: #fff;
    text-decoration: none;
    text-transform: uppercase;
    font-size: 90%;
    }

.main-nav li a:hover,
.main-nav li a:active {
border-bottom: 2px solid #e67e22
}

1.  Added a comment at the top of the page for our color orange since we will be using that a lot in the project

    _In order for this to work we need this border to exist before we actually hover over it_

2.  But since we dont want to see it we make it transparent
    EXAMPLE
    .main-nav li a:link,
    .main-nav li a:visited {
    color: #fff;
    text-decoration: none;
    text-transform: uppercase;
    font-size: 90%;
    border-bottom: 2px solid transparent;
    }
    1.  So now the orange border will only appear when hovered over, and it still exists
    2.  lets do the same with the buttons, we want a nice transition so we give them a transition: border-bottom of 0.2s
    3.  So whats the issue now? We want more space between the line and the text, right?
    4.  Theres an easy way to do this, we need to specify a padding for the link and padding is an inside space, so a space inside of the box which goes between the content and the border
        1. so we want a padding top and bottom of 8 pixels and left and right to have 0

_WE JUST FINISEHD BUILDING THE FIRST PART OF OUR PROJECT!_

# Section 5: Building the Features Section Part #1
