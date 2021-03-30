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

-this link does not go anywhere, its a dummy link until you know where you want to reference your link
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

1. What we will learn in this lecture:

   1. How to put content on a website directly from CSS with the after: pseudo-class
   2. We'll use the fluid grid for the first time
   3. We'll learn how to use icons

2. Lets create a section with the <section class="section-features">

   1. What is a section?
      1. in this its just like the header, it's a container so that we can tell this is a section.
   2. Now lets start with the title, and with the paragraph we will put that in a .row so lets create a <div> tag and give it a <div class="row"> because of course, we want this centered.
   3. Now lets create a heading here, but now each web page should only have one h1 element so only 1 main heading!
      1. lets make this an h2 for the rest of the sections
   4. So now copy the contents of section one and create the corresponding elements to them
      1. so we want a bigger dash than the - provided in the title, lets use &mdash;
         1. &mdash; it is special character
   5. Now lets create a paragraph <p></p> and give a class <p class="long-copy"></p> because it its a long paragraph and copy means for copyright which is like text for websites.
      1. lets paste the long text in the paragraph

3. So now lets start using the grid like a pro and in order to do that we have to start a new .row and inside of this .row we make a <div> for each col

   1. Now each column needs a col class and this comes here from the grid css files and we dont have to worry about it we just have to .col class
   2. Now we have four columns so each of those four columns will have this class span-1-of-4 from the grid file
      1. each column will have a width of 23.8 percent
   3. So lets create a new heading and since we already made h1 and h2 lets make an h3 and div col for all the headings:

    <div class="row">
                <div class="col span-1-of-4">
                    <h3>Up to 365 days/year</h3>
                    <p>Never cook again! We really mean that. Our subscription plans include up to 365 days/year coverage. You can also choose to order more flexibly if that's your style.</p>
                </div>
                <div class="row">
                <div class="col span-1-of-4">
                    <h3>Ready in 20 minutes</h3>
                    <p>You're only twenty minutes away from your delicious and super healthy meals delivered right to your home. We work with the best chefs in each town to ensure that you're 100% happy.</p>
                </div>
                <div class="row">
                <div class="col span-1-of-4">
                    <h3>100% organic</h3>
                    <p>All our vegetables are fresh, organic and local. Animals are raised without added hormones or antibiotics. Good for your health, the environment, and it also tastes better!</p>
                </div>
                </div>
                <div class="row">
                <div class="col span-1-of-4">
                    <h3>Order anything</h3>
                    <p>We don't limit your creativity, which means you can order whatever you feel like. You can also choose from our menu containing over 100 delicious meals. It's up to you!</p>
                </div>
    </div>

4. Whats missing here? Our icons!! So lets fix that we will use a beautiful icon font called ion icons (ionicons.com)

   1. from the pack we downloaded we have a lot of files but we only need two things
      1. we need these CSS files and these font files
      2. So how do we use these icons? We want them right in front of header <h3> elements
      3. First lets link the css file associated with the icon pack

   <link rel="stylesheet" href="vendors/css/ionicons.min.css" />

5. Lets use the ios themed icons
   1. so we write <i class=""> to call the icon we want we use its class.
      1. For the <h3>365 days a year</h3> we want something that represents 365 so we will use the infinity symbol
         <i class="ion-ios-infinite-outline"></i>
      2. For the <h3> Ready in 20 minutes</h3> we want maybe something with a watch or a clock
         1. <i class="ion-ios-stopwatch-outline"></i>
      3. For the <h3> 100% organic</h3> we want maybe something with a vegetable or healthy food
         1. <i class="ion-ios-nutrition-outline"></i>
      4. For the <h3> Order anything </h3> we want maybe something like a shopping cart
         1. <i class="ion-ios-cart-outline"></i>
6. Alright so this is our HTML, in the next lecture we will format this so it looks professionally designed.

# Section 5: Building the Features Section Part #2

1.  First thing we are gonna do to work on this is use white space! Do you remember that white space is a very important thing, so let's define white space between the sections for all sections at the same time
2.  So lets make this code in the reusable components section in our css sheet
    1. we can use padding to achieve this, normally we would use margin to style, but we are gonna use padding because we will have some sections with background colors and in order to preserve that background color we need to make sure that the space is inside of each of the boxes
    2. we want a lot of white space so maybe 80px on the top and the bottom, and 0 at left and right so no margin
3.  Next, we are gonna format the h2 heading here, we want it to look similar to the h1

    1. want it to hasve the same text-transform, letter-spacing, and font-weight
       h1,
       h2 {
       font-weight: 300;
       text-transform: uppercase;
       letter-spacing: 1px;
       }

       h1 {
       color: #fff;
       font-size: 240%;
       margin-top: 0;
       margin-bottom: 20px;
       word-spacing: 4px;
       }

4.  we want h2 to have maybe 180% font-size not so big and a word spacing of 2px. also want to align it inside of the row so lets have the text-align set to center.
5.  lets add some space between the h2 and its paragraph by giving h2 a margin bottom of 30px;
6.  Now we want a nice little yellow line between the h2 and the text, and as we were told we are going to use the psuedo class :after
    1. after is just some stuff that will appear after the H2
    2. style it like a normal element
    3. after we specify an after pseudo-class, we have to specify its content
    4. in this case we dont want anything in it so we put a blank space " ";
    5. give it a width
    6. we want to center it so give it a margin of 0 auto;
    7. need to specify some margin between this and the bottom so give it a margin-top of 30px;
    8. there is a margin between the h2 and the h2 after block
7.  So now lets define a nice paragraph style for this remember we used .long-copy

    1. give it a `line-height between 120 and 145%`
    2. this line is very long another rule of typography was that this line should have at least 2 complete alphabets, and this is way more
       1. so let's make this paragraph a little less wide
    3. So the problem is that it will no longer be centered, so a good idea for this problem, is instead of trying to center, we should set margin left to 15%
       1. WHY 15%? because the total width would be 100 percent so if we want to center it the remaining 30% should be distributed to both sides.
          1. so 15% left, 15% right, plus the 70% (which is our width) makes 100%

8.  Next lets format the boxes, first thing wrong is the columns are a little too close to each other
    1. to remedy this lets give some padding here like 1%
    2. we dont want to change the grid rules that we have for our colummns so we will create a new class and call it box
       1. <div class="col span-1-of-4 box">
       2. this box class will go in the reusable code section receives a padding of 1%
       3. also we are gonna add h3 to the h1, h2 because we want these three attributes to be always the same so we maintain a similar style throughout the webpage for our headers
          1. font-weight: 300;
             text-transform: uppercase;
             letter-spacing: 1px;
    3. We want h3 to be a little bigger than normal font-size but only slightly bigger so maybe 110% and add some space between h3 and their paragraphs
    4. So whats the issue now?
       1. I personally didnt have this issue while making this project, but in the video lecture the letter spacing between the h3 titles were too big and caused them to go down to the next row so in the lecture he took out letter spacing from the big connection of h1,h2,h3 and only added letter spacing to the h1 and h2 specific elements code block
    5. Whats the issue now? The text is kind of overwhelming
       1. lets make the text a little bit smaller and raise its line height
       2. lets target .box p and give them a line-height of 145% and font-size of 90%. (THIS LOOKS SO MUCH BETTER!!!!)
    6. Next, lets fix the icons and make them a little bit bigger
       1. to do that we must make a new class for all of those icons
       2. lets make a class and call it icon-big
       3. lets put this in its own section of code for the css sheet, put it below paragraphs
       4. so since icon font is just a font give it a font-size of 300% if its too big we can always reduce it
          1. display it as a block so it forces a line break
          2. give it the color orange like our buttons
          3. give it some margin between icon and heading (margin-bottom);

# Section 5: Building the favorite meals section Part 1

1. What we'll learn in this lecture:
   1. How to make a grid of beautiful images
   1. How to make a nice "zoom-in" transition, only using CSS
   1. A way to make <img> elements darker
2. Back to our HTML file, how are we gonna build this grid?
3. FIRST we need to build a new <section> and give it a class of meals <section class="section-meals">

   1. we want two rows with four images in each row
   1. we will not use the row class here because we dont want a centered row with some images
      1. we want our images to occupy 100% of the browsers width
      2. it is actually good practice to use an unordered list <ul></ul> to do that: in fact, two unordered lists
         1. one for each line

4. Inside of our <li> we will use <figure> its like a container which can contain an image and also a caption for the image, but in this case we will only put the image as the caption may be too much to learn at this moment.
   1. <figcaption> is what we would use to give figure a caption.
   1. next we put a <img src=""> inside of the <figure>, and where is our image?
      1. in the source folder the pictures are in order from 1-8
      2. give them their alt texts
5. So lets format the images now because they are just in a straight line lol with CSS
   1. CREATE a new section in CSS for MEALS\
   2. remove bullet points with list style: none;
   3. another thing since we want this to be the entire browser width we give a width of 100%;
   4. NEXT, format the <li> so target .meals-showcase li
      1. give them a display: block;
      2. float them to the left (encourages them to be side by side)
      3. ANOTHER VERY IMPORTANT THING is their width
         1. we have 4 li elements and we want them to take up 100% of the page so each <li> needs to be 25% wide;
   5. NEXT, lets give <figure> a class of meal-photo <figure class="meal-photo"> and give it to all 8 figures
      1. now lets format .meal-photo and give it a width of 100%.
      2. NOW, saying that this element with the class "meal-photo" has a width of 100% means just that it has the exact width of its parent, which in this case is .meals-showcase li
         1. give it a margin of 0 i know we have it declared earlier in the file with the h1 element with the normalize css file it defines some margin for that element so we have to overwrite that specifically
   6. NOW, lets format the actual image inside of the photo container and the most IMPORTANT thing i have to do is again, width equals 100%
   7. In the next lecture we are going to add transitions to the images in the li elements.

# Section 5: Building the favorite meals section Part 2

Now the first thing we notice and we didn't correct yet is this large distance between these two section which doesn't look natural and thats because it has a big padding that brings it almost half way to the page.

We actually dont want padding in this section because its a different section.

                        .section-meals {
                        padding: 0;
                        }

Now lets work on animation, what animation we will be using is that when we hover over one of the images, the image kind of zooms out and also gets brighter

So we are gonna use the property of transform and give it scale of 1.15, this means instead of 100% it will be 115% big - so as you can see now they are bigger than they are supposed to be and you see they even go out of the browser width - lets fix this we dont want them to be bigger than thier container, it kind of overflows? right? - there is a property called overflow, and if we set it to hidden then that overflow will not be visible and you will only see part of the image which is still inside of the container

Now we can use the :hover state pseudo class for everything on .meal-photo img and give it a transform scale value of 1 and now when you hover over the image it zooms out

- there is a little bit of issue with the zoom out because on some photos it shows a white line when the img zooms out - to fix this set it to 1.03 instead
  We also want to animation this so, how can we do this? - transition: transform 0.5s like we did with our links remember? - this looks so cool now!
  Now lets take it another step further we want to make the imgs darker but when hovered over it makes them brighter
  -opacity lets set it to 0.7 which is 70% - so why is it white? because the background color is white, so if we want tho make this darker we need to set the background-color of the img to black. it will make it darker

Now we need to animate the opacity so that when we hover, we also want the opacity to change back to 1 which is 100%

    .meal-photo img {
    opacity: 0.7;
    width: 100%;
    height: auto;
    transform: scale(1.15);
    transition: transform 0.5s, opacity 0.5s;
    }

    .meal-photo img:hover {
    opacity: 1;
    transform: scale(1.03);
    }

in order to animate it we put the opacity 0.5s in the transition property in the .meal-photo img. Mow we should we both of the things animated.

Another thing we could fix on the page since, most of this section is done is that we need to add some space between the paragraph and the icons. Instead of targeting all long copy classes you can specify to just the features section long copy paragraph

make a new section for features in CSS

                .section-features .long-copy {
                    margin-bottom: 30px;
                }

# Section 5: Building How it Works Section Pt1

What we'll learn in this lecture: - how to draw circles with CSS - a cool technique to make separations between sections - how to incorporate App Store and Play store buttons

First lets start off with making a new section <section class="section-steps"> and copying the information from the clients documents
-this time we have two columns and not 4
-in our first column we want our iphone - in our next column we actually want 3 containers which will then contain the number of the step and the corresponding text

<div class="works-step"> - the numbers themselves will be a div element

            <div class="col span-1-of-2">
          <div class="works-step">
            <div>1</div>
            <p>Choose the subscription plan that best fits your needs and sign up today.</p>
          </div>
          <div class="works-step">
            <div>2</div>
            <p>Order your delicious meal using our mobile app or website. Or you can even call us!</p>
          </div>
          <div class="works-step">
            <div>3</div>
            <p>Enjoy your meal after less than 20 minutes. See you the next time!</p>
          </div>

Now lets add the app store buttons and the buttons are very simple remmber they are just links
<a href="#" class="btn-app"></a>
we will add the img inside so the img becomes the button
<a href="#" class="btn-app"><img src="resources/img/download-app.svg" alt="App store button"></a>

Now we need to format this section.

# Section 5: Building How it Works Section Pt2

lets make a new section in CSS called _How it Works_

1. Now lets format the .steps-box
   1. give them a 30px margin-top from h2
2. How do we select the boxes individually? we can use this new pseudo class called :first-child 1. What does :first-child do? it selects the first of the steps-boxes which is the left one 2. Theres a similar command called :last-child
3. So now lets text-align first child to the right! BUT WAIT?! There is no text. However, thats ok text-align property doesn't work only for text, it actually does work for all inline or inline block elements and the image is one of those inline block elements
4. Lets add a padding-right to it and give it 3%. BUT WHY 3% instead of a pixel value? Theres a simple reason it has to do with responsive web design
5. Now lets target .app-screen image and give it a width of 40%.

Next, we want to format the numbers in the div elements, we want them to be a circle with a number inside and we also want some distance and some space
-give .works-step a margin-bottom of 50px - and then target the div of .works-step - give it the color orange we have been using, give it a border of 2px solid with the same color, and give it an inline block because that way we can ensure that the element doesnt force a line break so we can be sure that the number will be side by side with the text.

Next, the number is now a square after the formatting but we know how to fix this.

- Change the border radius to 50% - give we can now define the height with 50px and width 50px, it has to be as high as it is wide - make the number centered so text-align centered - next we need to add padding 5px and font-size 150% to change the numbers - we also want the paragraph next right next to the numbers so we float left and give it a margin-right of 25px;

Now, lets make the buttons the same size so we target .btn-app img and give them a height of 50px a width of auto, and margin-right of 10px
-we also want the buttons more toward the bottom of the phone

EXAMPLE we will use a new selector called :last-of-type

-this will target the last child element of the same type so in this example only the buttons will move down
.works-step {
margin-bottom: 50px;
}  
 .works-step:last-of-type {
margin-bottom: 80px;
}
-everything else will keep their margin except for this last type it will have 80

What is the issue now? Even though we defined that this section should have 80px padding this section did not have the padding when inspected in the Chrome Tools. It actually shows that it has a 0px. This is because - we didn't clear our floats

_Clearing Floats_

We use a very special selector for this task which is very used in web design
EXAMPLE
.clearfix {zoom: 1}
.clearfix::after {
content: '.';
clear: both;
display: block;
height: 0;
visibility: hidden;
}

this will clear the float after an element, now lets add this class to our ul in .meals-showcase
-WHY? the child elements of this class, which would be <li></li> have the float property and so we say that the parent has this clearfix class and then that float will be cleared right after the ul element

It is _IMPORTANT_ in web design that we want to show that this is a different section so lets give .section-steps a grayish background color.
-very subtle effect here
-background-color: #f4f4f4;

# Section 5: Building the Cities Section - Part 1

In this lecture we will learn:

- practice our new skill set
- how to use small icons aligned with some text
- how to style generic links

Lets start off with a new section and call it <Section class="cities"> and give it a <div class="row"> and then lets copy the information from the pages section of what our client wants in this area

EXAMPLE

Section 4: Cities
Title: We're currently in these cities

Lisbon
1600+ happy eaters
60+ top chefs
@omnifood_lx

San Francisco
3700+ happy eaters
160+ top chefs
@omnifood_sf

Berlin
2300+ happy eaters
110+ top chefs
@omnifood_berlin

London
1200+ happy eaters
50+ top chefs
@omnifood_london

MY EXAMPLE attempt

In this I paused the video after the lecturer told us to give it a try ourselves before continuing this next part.

First we created a div row and inputed 4 <div> because there were 4 city columns that we need to create, so we made <div class="col span-1-of-4 box"> and each div had its own img, h3 with the city name, paragraph with a <br> in it with the followers and chefs, and then a link to their twitter handle.

Before we continue, what is needed to be fixed? images we need to style them appropriately and give them some padding from the top h2 because they are way too big and need to be smaller

The LEC attempt

-instead of p with a br in it and a link at the bottom he decided to go with icons for the happy eaters, the chefs, and the usernames

         - <i class="ion-class-person"></i>

Next we're going to add the text and other items in a container so make a div class called city-features and then make 3 seperate divs for eaters, chefs, and twitter handle

<div class="col span-1-of-4 box">
<img src="/resources/img/lisbon-3.jpg" alt="Lisbon" />
<h3>Lisbon</h3>
<div class="city-features">
<i class="ion-ios-person"></i>
1600+ happy eaters <br />
</div>
<div class="city-features">
<i class="ion-ios-star"></i>
60+ top chefs <br />
</div>
<div class="city-features">
<i class="ion-social-twitter"></i>
@omnifood_lx <br />
</div>
</div>

Now do this for the rest of them with their appropriate icon. In the next lecture we will style this section with CSS. Thats the end of part - 1.

# Section 5: Building the cities section - part 2

LEC

Now formatting this shouldnt be so hard right? Format the images on your own

MY EXAMPLE

we want to target the box class and we want the image to be exactly as wide as the box - give it 100% width; - height will automatically adjust to that with auto - we want a margin to the bottom to give some space between the box and h3

- OK COOL this looks great now lets add some margin between the icon lines
- if you remember each of those is a Div called city-features give it a margin-bottom of 5px;

_DIFFICULT_

How do we format the icons? How do we make them a little bigger and maybe aligned to one each other and have an orange color

1.  If you remember for the other icons we named the icon-big class, now lets make an icon-small class for the icons
2.  traverse back to the icons section in the css file
3.  first lets make them aligned to each other text-align: center, give them display: inline-block, width of 30px and the color we've been using for the rest of the project #e67e22.
4.  and then if you remember icons are a font so change the size with font-size and make it 120%
5.  Now you notice that the icons are not quite aligned with the text 1. give it a line-height of 120% 2. give it a vertical-align and set it to middle and maybe that will fix our issue
6.  The issue is now the icons are further down than the text, how do we fix this?

LEC There are 3 secrets essentially to align text and icons
line-height: 120%;
vertical-align: middle;
margin-top: -2px;

-with margin being negative it does the opposite thing than a positive margin
margin-top: -5px this will hopefully pull our icons up instead of pushing them down

-lets also give it a margin-right of 10px so the text and icons arent so close together

7. Last thing to do in this section is to turn the twitter handles to links and to style the links with CSS
   1. give them all a links
   2. next we want the color of the links to be orange and we want a more beautiful underlining
      1. lets create a new section called generic links in CSS because we will use these links in more places maybe
      2. target a:link, a:visited (_a:active wasn't working for some reason?_)
      3. lets create a new underline using border-bottom 1px solid #e67e22;
      4. padding-bottom 1px so we have some space between the text and the border
   3. So now what we want to happen when we hover over a link we want it to become the color of the normal text, which is gray from the html area
      1. next we want the border to disappear. How do we do that? instead of 0px we make it transparent and makes it a cleaner solution
      2. we want a nice transition too so we pick transition and select border-bottom and give it 0.2s and color 0.2s as well.
8. We have an issue now under the google play store and app store where we can an annoying underline whenever we hover over the buttons since they also have the a link
   1. So now we go back into the how it works section and create some code for btn.app give it the link and visited and then give it a border of 0. Now the border is gone GOOD!

Now we have 5 of our 9 sections complete, we are more than halfway there! Next we have the customer testimonial section.

# Section 5: Building the customer testimonial section - part 1

Once again we will use beautiful imagery to almost make the user feel hungry. Here we have 3 customers side by side and what they have to say. This is a common way of showing customer testimonials.

In this section we will learn:

1. How to create a beautiful background-image effect
2. How to effectively communicate what customers have to say

EXAMPLE

Section 5: Customer testimonials
Title: Our customers can't live without us

Omnifood is just awesome! I just launched a startup which leaves me with no time for cooking, so Omnifood is a life-saver. Now that I got used to it, I couldn't live without my daily meals!
(Alberto Duncan)

Inexpensive, healthy and great-tasting meals, delivered right to my home. We have lots of food delivery here in Lisbon, but no one comes even close to Omifood. Me and my family are so in love!
(Joana Silva)

I was looking for a quick and easy food delivery service in San Franciso. I tried a lot of them and ended up with Omnifood. Best food delivery service in the Bay Area. Keep up the great work!
(Milton Chapman)

1. First lets start off with making a row for just our h2 element, and then lets make another row and then another div with col span 1 of 3
2. Second, theres actually an HTML element that's designed to precisely include quotes into HTML documents. It's called <blockquote></blockquote>. We will use this instead of <p></p> And we have an element to put for the name of the person the quote belongs to this goes inside the <cite> element the img element can go inside the cite element because we want the picture to be shown.

This is the end of this section. Next time we will format this section in the following update.

# Section 5: Building the customer testimonials - part 2

Lets start by building the beautiful background img. The file belongs in our resources/css/img

REMEMBER all background images go right here into this folder
lets style the .section-testimonials give it the background image, and lets change the linear-gradient because the picture is way too bright;

1. Now lets make all the text inside of this area white give it a color of #fff
2. Now we are gonna do something with the background images in CSS.
   1. By giving it a background-attachment of fixed, this allows you to scroll the website and the image will stay the same and not move
   2. DO THE SAME THING TO THE HEADER
3. Now lets fix up the <blockquote></blockquote> elements
   1. first maybe we want some padding because the images are a little too close to each other give it 2%
   2. it is very custom to have the customer text it italics (Now we can do this only because of our google italic font style at the top of our HTML page)
   3. give it a line-height of 145%
4. Now target <cite>
   1. give it a font-size of 90%
   2. margin-top 25px;
   3. give it a display block to force a line break between the text and the img
5. Now target <cite:img></cite:img>
   1. veritcal-align the img to the middle
   2. give it a height of 50px; (maybe thats too big)
   3. border-radius of 50% because that makes everything round
   4. give it a margin-right of 10px;
6. What else is missing here?

   1. We need a big quotation mark, which we can put in the middle of the page. We can add that with the selector class :before because we want it before our text
   2. _IMPORTANT_ Remember how do we put text on a website? we use the content: "A";
   3. we give blockquote:before a content and a font-size
   4. In order to put the quotation marks there is not as easy as it may sound because in order to do that we need to use something called an iso selector

   A. *www.css-tricks.com/snippets/html/glyphs/*

   5. after going to that link we ctrl + F and search for quotation marks to find how to implement it to our page we want left double quotation mark
   6. we copy the code from
      EXAMPLE
      p:before {
      content:"\201C"} - we copy the \201C part of the code

7. So we need a new line so we need to make blockquote:before a block element

   1. If we want to position this we need to define its top and left attributes because its the easist way to change it with absolute positioning
   2. Before we make an element absolute positioning we need to make sure that its parent is relative
      1. What would happen if we didnt do this?
         1. if we didnt do this blockquote:before would not appear where we want it

8. So after adjusting the blockquote:before we realized it was too close to the text, what can we do to fix this?
   1. lets try putting the top to -5px maybe and left to -3px
   2. So now maybe we should give it some space between the line created under the h2 and the block quotes, what do we do?
      1. In order to have more space for the quotation marks and to make it bigger, set it to 500% and give it a margin-top of 40px

Thats the end of this section!

# Section 5: Building the Sign-up Section - part 1

What we'll learn in this lecture:

- Design with border radius
- How to create box shadows with CSS

EXAMPLE

Section 6: Sign up and pricing plans
Title: Start eating healthy today

Plan 1: Premium
399$ per month
That’s only 13.30$ per meal
1 meal every day
Order 24/7
Access to newest creations
Free delivery

Plan 2: Pro
149$ per month
That’s only 14.90$ per meal
1 meal 10 days/month
Order 24/7
Access to newest creations
Free delivery

Plan 3: Starter
19$ per meal
1 meal
Order from 8 am to 12 pm
Free delivery

create a div row and inside it put an h2 element with this sections title. Then create another row and as youve seen in the lecture that we have 3 columns.

1. How are we gonna organize our codes into these boxes, inside each of these boxes?
   - first we need to make a <div class="plan-box"> and within it we need to make 3 separate divs
   - In the first div we want to put our h3 element in there
   - next we want each paragraph to have its own class
   - EXAMPLE
       <p class="plan-price">$399 / month </p>
       <p class="plan-price-meal">That’s only 13.30$ per meal</p>
   - Now we will use a <ul></ul> element for the other items and put some <li>
   - and inside the <li> lets put an icon of a check mark from ionicons.com, lets look for our ios inspired icons and look for a checkmark
   - <i class="ion-ios-checkmark-empty"> and then the text that we want here
   - next lets create the sign up button this should be pretty easy because its just a sign up button and we already had that before
     - <a href="#" class="btn btn-full">Sign up now</a> our class is the button class we used before and we will give it the full one because
     - instead of deleting our empty element in our li area we can give it the crossed out icon
     - we also only want the premium button to have the full class so give the other buttons the ghost class

That's the end of this section. In the next one we will work on CSS styles.

# Section 5: Building the Sign-up Section - part 2

1. First thing we will do is change our background color to gray because we have a theme of alternating background colors.
2. Then we will start to format the plan-box, lets give it a white background so it stands out from the other background
   1. next we want rounded corners so lets set the border radius to 5px
   2. we dont want it to have 100% of its parent element width so lets give it 90%
   3. Now lets center it within its parent and if you remember we need the child element to be absolute and the parent element to be set to relative
      1. Who is the parent cell of plan-box? it is col span-1-of-3 box
   4. Now lets divide this into the three sections
   5. LEC explain why we put this box into a column
      1. we have this box inside of the column, because if we hadnt we wouldnt be able to make the plan box as wide 90% or change the background color. It would not be possible by just formatting this column or adding some box after the span class
   6. Now lets section these into subsections in order to do that we need to call it like this .plan-box div {}
      1. because as we defined it, we have three divs
      2. give it a padding of 15px and a border-bottom color of subtle color change from #fff to #e8e8e8
   7. Let's continue we now want to change the size of .plan-price because our h3 is already styled to how we want it and we wnt .plan-price to be really big, now it kinda looks overwhelming at 300% font-size, but lets deccrease the font-weight to 100 and change the .plan-meals-price paragraph to make it smaller by 90% font-size
   8. Now we want the per month statement to look different heres another HTML element to help with that
      1. <span> it has only one purpose, its purpose is to just appear inside a paragraph, for example, and style some text in a different way than the rest
   9. When we style the .plan-price span the thing is here that this span here is a child element of the .plan-price element which has a font-size of 300%;
      1. Now if we say the child font-size equals 100% then this 100% would not be the base size of 20px but this 300% because it is the parent font-size so if we want it smaller, we need to go with a smaller % maybe like 30%.
      2. another thing is we want the font-weight back to 300 in .plan-price span because the parent element font weight is 100 so we have to specifically say that this is 300 otherwise it will inherit the parents 100
      3. and then make the parent .plan-price orange #e67e22
   10. Now we will get rid of the lists here give the .plan-price ul a list style of none
       1. Now we will add white space between those list elements so we can say we want the top and bottom to have 5px and 0 to the left and right
   11. One thing we forgot to do was style the icons in this section, we forgot to give the small-icons class since we have that class styled
   12. What's wrong here? because we left that paragraph empty on the Starter box, we have a weird formatting issue so the line doesnt appear. How do we fix?
       1. So we need to put a space there we need to use a special character and for a space its &nbsp;
          1. &nbsp; gives us an empty space
       2. Next, we want to center the buttons. A good way to simply do that is to select the .plan-box div:last-child
   13. So we have a gray line at the bottom of our boxes and we dont want that so lets style that out so we want the last div to have the line gone
       1. first lets add some gray background to our first div to change it
          1. the key here is being subtle, we want to make a difference, but a difference that doesnt pop out so much
   14. LETS DO SOME BOX SHADOWS
       1. first give it a border-top-left-radius and border-top-right-radius of 5px
       2. Now lets add a nice box shadow to the entire box .plan-box
       3. the first value in box shadow: x-axis offset - we dont want any so we put 0
       4. the second value in box shadow: y-axis offset - we want 2px
       5. the third value in box shadow: blur - we want 2px
       6. the fourth value in box shadow: color - we want want subtle gray here again #efefef

We only have one more section left and the footer!!!!!

# Section 5: Building the Contact Form - part 1

In this lecture we will learn:

- how to use a set of new HTML elements and create forms: form, label, input, select, option, textarea
- how to style these elements

1. Let's create a new section called .section-form
   EXAMPLE
   Section 7: Contact form
   Title: We're happy to hear from you

Fields to include:
Name
Email
How did you find us?
Newsletter
Drop us a line

2. then let's create our form and we will do that in a row <div class="row">
3. <form> - is for a group of input elements where we keep them all together
   1. it requires a couple of attributes:
      - method="post" : we will put post here, but this is not relevant for us in this case, because this is only needed when we send this form and that requires a lot of programming in other languages
      - action ="#"  : which is like a link so it is empty in this case, the action could be the script which handles how the form will be sent, which again we will not talk about in this course 
      - class="contact-form"
4. Now we can fill this form with our elements we will now put a couple of rows inside, and in each of those rows we will have our different input elements
   1. EXAMPLE
      1. so we will have one for name, email address, or something like that
      2. and then one column for the input eleement
      3. We also want one colummn to be bigger than the others
         1. so we will say one will have a col span-1-of-3 and the other col span-2-of-3(this column will be twice as wide) because now these 2 columns now make a row
5. In the first column we want the label, and theres an HTML eleement for that, called <label>

   1. first lets make the <label>Name</label> and thats it for this col span-1-of-3
   2. in the next row span-2-of-3 we make an input element
      1. <input> requires a:
         1. type ="text"
         2. name ="name (we will call it name for now)" (which will be used later to send that form)
         3. and it requires an id="name", which we will also call name
         4. next we do placeholder="Your name" and inside it will hold that text in the input field until changed
         5. required> and if we use this the browser will not allow us to send a form without completing this field.
   3. Ok so now make this for the other parts like email
      1. you can change the type to email(its true theres an html element for it), name, and id to email and the placeholder
   4. For the How did you find us, maybe lets put a little dropdown box

      1. remove the input element, we will not use this
      2. use the <select> element

         1. name="find-us"
         2. id="find-us"
         3. then we put the <option></option> element inside of the select container

            1. each option needs their own action
            2. we need to specify a value, value="friends" is the source then for the script that will handle the form once the form is sent, which we will not cover in this course
            3. in the <option> tag if you put selected inside it that option will be what appears first in the dropdown menu and will be selected

            EXAMPLE
            Dropdown menu first item : Friends

            1. friends ✅ 2. search engine 3. advertisement 4. other

   5. Next lets make the newsletter we will use checkbox for this one

      1. checkbox is a box where you can choose your options
      2. we will give it a default of checked

      <div class="row">
            <div class="col span-1-of-3">
              <label>Newsletter</label>
            </div>
            <div class="col span 2-of-3">
              <input
                type="checkbox"
                name="news"
                id="news"
                checked
              />
      3. and then we will put some text after the input tag, like Yes, please

   6. Now lets add the drop us a line part copy the newsltter section
      1. in this we will use <textarea> and it will need some attributes
         1. name="message
         2. placeholder="Your message"
   7. Now lets add a submit button
      1. we dont want anything in this sections label because we want it to be aligned with the fields of this form
      2. give it a &nbsp;
      3. input type of submit
      4. value is Send it!

LEC

Why did we use ids?

-Simple reason, because here in the label we can use the `for` attribute and then put the name of the ID here for="name" after doing this it kind of link the label with the input

Now when we click the Name on the webpage, then the field gets selected
-this will not work with a checkbox and neither with the text area

# Building the contact form section - part 2

Ok now let's use CSS to style our contact form

1. First issue, these elements dont fill 100% of their column
2. Second, we clearly dont need all the entire width of the parent element of this row here
   1. because there is way too much space between the labels and the elements
3. Lets start a form section in our CSS file and target .section-form
   1. lets give it a width of 60%
   2. we also want to center that thing and we can use that technique where we say that we want the left margin to be 20% which is half the difference between 100 and 60
      1. but in this case we will format this the other way which is giving it a margin top and bottom of 0 and set its left and right to auto to center it
         1. margin: 0 auto;
         2. this will center this contact form inside its parent element
   3. Now lets format the other elements, such as input and the other was select, and textarea
      1. we want to give them a width of 100% because we want them to take the entire width of their cell
      2. we also want them a little bigger so lets add some padding 7px inside of them
      3. give it a border-radius of 3px.
         1. We have a tiny error, in the video his bars are stretched more than mine(ITS BEEN FIXED) ✅
   4. So the submit button and the newsletter take up their whole width while we only want the first two elements to fill. What do we do?
   5. We are going to use a new css selector and with them, we can select all input elements which has the type of text
   6. it goes like this input[type="text"]
      1. Now the buttons are smaller, but we want to remove this weird border color so lets do it.
         1. give it a 1px solid #ccc gray border
         2. you may notice that the select container doesnt fill the width like the others, but we are going to leave it as is because its hard to style select elements
   7. Now, we want this textarea to be a little bigger give text area a width of 100px, and we want this send button to look like other buttons (the full button)
      1. to do this we simply add input[type=submit] to the button section like this:
      2. EXAMPLE

.btn:link,
.btn:visited,
input[type="submit"] {
display: inline-block;
padding: 10px 30px;
font-weight: 300;
text-decoration: none;
border-radius: 200px;
transition: background-color 0.2s, border 0.2s, color 0.2s;
margin-right: 15px;
}
and we also want it with the btn-full:link and :visited spot

.btn-full:link,
.btn-full:visited,
input[type=submit] {
background-color: #e67e22;
border: 1px solid #e67e22;
color: #fff;
}

and we also want the hover effect too so add it to :hover, :active input[type=submit]:hover, input[type=submit]:active

- that should take care of it!

8.  So now we notice that the space between the newsletter is kinda cramped compared to the rest of the areas, lets add some space
    1. we also want to get rid of these blue borders that
    2. First, lets format the checkbox? how do we target that in CSS?
       1. input[type="checkbox"]
       2. we want all sides to have margins: 10px 5px 10px 0;
       3. and lets get rid of those borders when we focus on those elements, the best way to do that is to get rid of it for all elements
9.  We have another zero class here which is called focus
    1.  \*:focus {outline: none;} and it should go away
10. Ok now so the outline is gone, and we now have space between those elements, which looks so much better now.

Thats the end of this part. All that we have left to do next is the footer section.

# Section 5: Building the footer - part 1

In this section we will learn:

- how to build a simple but effective footer
- a cool way of using social icons

So for the footer HTML has another special element jsut for that and as you can imagine its called exactly <footer>

1.  first lets maker the <footer> and inside it lets give it a row
2.  at some point we will have two <nav> inside of this row
3.  first, lets make some cols and give it a span-1-of-2
    1. the first one is for navigation
    2. the second col is for social media
4.  As you remember we're going to use an unordered list in order to build that navigation
5.  Now lets see what we need from the clients pages

Section 8: Footer
Title: None

Navigation:

1. About us
2. Blog
3. Press
4. iOS App
   5. Android App

Also include links to facebook, twitter, google+ and Instagram accounts. 6. So we create the <li> and inside we put the <a> links in there 7. Then, for the next navigation we are going to include links to facebook, twitter, google+ and instagram account

1. but obviously we wont write the word in there, but we will use icons from ion icons
2. <li><a href="#"><i class="ion-social-facebook"></i></a></li>
   <li><a href="#"><i class="ion-social-twitter"></i></a></li>
   <li><a href="#"><i class="ion-social-googleplus"></i></a></li>
   <li><a href="#"><i class="ion-social-instagram"></i></a></li>

3. After we finish the navs we usually put a paragraph at the end where we have some fancy text about copyright or something like that
   1. lets include another row and inside that we put paragraph and we use &copy; for the copyright symbol
   2. Copyright &copy; 2015 by Omnifood. All rights reserved.
4. When we look at the page mow it looks kinda funky because the links and icons still have our previously formatted styles.

That's the end of this lecture! See you in the next one that we format!

# Section 5: Building the Footer - part 2

1. First we want the links to be side by side, and we want to get rid of these bullet points, and we want to format the whole thing. We also want a very dark background in order to make it stand out
   1. lets start with the background here in <footer>
      1. background-color: #000; of course not black but we want it kind of deep so #333.
   2. Lets format the navigations .footer-nav
      1. lets get rid of its list style give it none, and float it on the left of inside its container
   3. for the .social-links we give it a list-style of none, and float it to the right
   4. On the list elements inside of these navigation of these unordered lists 1. we want to have them side by side and so one thing we can do is to display them as inline blocks so we dont force a line break so they will be side by side 2. and we can also assign them some margin to the right with 20px.
      LEC

So now they are side by side, now there is only one tiny problem left with these li elements and let me show you what im talking about
ISSUE: You can see the row class and that there is space between the last icon and the end of the row right?

1. So when we inspect the element the big blue highlighting area is our row div. as you can see the last icons does not go all the way to the right side of the row and thats because of our MARGIN-RIGHT we defined of 20px.
2. So what do we need to do? so what we need to do is get rid of that for the last li element
   1. so we target their :last-child elements for .social-links and .footer-nav and then give it a margin of 0 or margin right of 0 its the same
3. So now lets work on the links and their colors
4. so we target .footer-nav li a and .social-links li a (we put a to target the links inside of li)
   1. and we give it the :link and :visited
   2. so now we of course want no text-decoration
   3. we want no border because we defined it all the way at the top in the links section
   4. we also want a nice text color for them so #888
5. Alright, so it looks a little dark, but it's on purpose because then I will then with the hover effect make the color look lighter because we dont want to stand this out too much
6. now lets add some hover effect to the links here first lets target :active and :hover
   1. give it a color of #ddd
   2. we also want to have a transition on the link and visited section
      1. give it a color transition of 0.2s
7. Of course we need some padding in our footer not as big as our other sections but give it 40px
8. then we want to target the footer p and give it a color of #888 and align the text to the center and give it a smaller font size because its not necessary that its big as the main text on website
9. lets add some distance between this paragraph and these navigations so the best way of doing that is to add a margin to the top of the paragraph 30px
10. So of course, this looks a little empty here right now, because you could actually add some more text here or idk something else in this case we will not worry about it
11. So now we are gonna change the font size of the icons and we are gonna do a little cool thing when we hover over them we will give each icon its corresponding color for its _social media_ color
    1. USE https://www.designpieces.com/2012/12/social-media-colours-hex-and-rgb/
    2. So with facebook we will change to #3b5998
    3. with twitter it will be #55acee
    4. google + will be #dd4b39
    5. instagram #e95950
    6. So lets make a block for .social-links li a so we can format the icons font size
       1. give it 180%
    7. Now we are going to target each icon the best way is to just take their class name and add the hover effect to them
    8. the icons are too big but the colors work lets add a transition so target the icon classes and add a transition color 0.2s
    9. Ok so all the text in this area is too big so we are going to reduce it because this doesnt look too natural
    10. So we will edit the text in the footer element so it targets all elements so we will give footer a 80% font-size which will then everything will get effected inside of this element and deleted footer p font-size % and change it
    11. change the icon to 170% maybe
    12. lets fix the padding to 20px in footer p and the make the icons smaller to 160%

Lets look at our whole webpage now and see what we have here. Thats the end of section 5! In section 6 we will learn how to make the webpage responsive.

# Section 6: Making the webpage responsive - part 1

So we made it look beautiful on a computer, but how about on other devices with smaller screens?

So far we built our entire layout with a fluid grid and now its time to take care of media queries toi make our website truly responsive

Media queries are what will enable our website to call different CSS style declarations based on the current browser width or the width of a mobile device that displays our site

These media queries will trigger at different breakpoints
-breakpoints are screen width at which we want our website to change the way it looks in order to look good on all devices
The standard breakpoints are for tablet and for mobile. When starting out, the easiest way to define breakpoints is to use device widths of popular devices like iphones or ipads

However, when we get more experience we want our breakpoints to keep going to point where your design starts to look kind of terrible

1. So the first thing we're going to do is create a new css file for the media queries
   1. Now lets start with the smallest we call it with
      @media only screen and (max-width: 480px) {} and everything we want wqill go in the declaration block. So this means the width of the device or browser is less or equal than 480px
   2. Next we will make a media query for larger small phones we will give it 767px because the width of an ipad is 768 so we want this to target all the phones smaller than the ipad
   3. This media query will target the ipad and of course other tablets as well. This one is 1023 pixels. So this will target the ipad in portrait mode which has 768 pixels. This breakpoint is 1023 because the iPad in landscape view is 1024 pixels
   4. This media query will target the ipad and other small computers. This will be 1200 because as you can remember our row was defined as 1140px so we want the website to change its look when it gets close to that value
2. We forgot to link the new media queries to our HTMl doc
3. Also there is something essential we need to do to the top of the head when you make responsive web design
4. its the <meta> tag and it needs a name="viewport" content="width=device-width, initial-scale=1.0"
   1. so what this will do is tell mobile phones for instance that they should not zoom out the page. That they should always start with the scale of 1
      1. initial-scale=1.0
5. Now we are ready to start writing some CSS inside of those media queries. In order to see how this works lets try iton the browser.

   ## @media only screen and (max-width: 1200px) {} "big tablet to 1200px (width of smaller then the 1140px row)"

6. Lets open up inspect elements on the chrome tools, in the top right corner it tells us the size of the window

   1. so you remember our first breakpoint was 1200 because if we look at the page and see at 1140px our page is very close to the sign up button and doesnt give it room to breathe this is why we use the 1200
   2. So when we make the page smaller our content (.hero-text-box) the goodbye junk food text disappears! How do we fix?
   3. so lets see what we can change here. lets copy the .hero-text-box CSS information and put it in the media query 1200 breakpoint group
      1. and now we will change the things we want to change here. we dont want the width to be fixed anymore we just want it to be 100%
         1. get rid of the other declarations we had originally copy and pasted inside the query and just leave the width 100%
         2. in order to create some space between the text and the border of the browser we need to add some padding
            1. give it 0 for top and bottom and 2% for left and right
         3. Now that box doesnt disappear!
   4. ISSUE: But now what we see here is the text is still completely glued to the screen like (the logo and the sign-up button they still need space)
   5. Lets check the html file, and these elements happen to be inside a div row
      1. now we will define something for all the row classes
      2. give it the same padding as the .hero-text-box which is 0 2% because we want to be consistent
      3. we are going to format this a little different though. When we have only one declaration in a block we write it like this (my vscode automatically corrects it tho 🤷🏿‍♂️) -- TODO look into fixing it tho, it makes the code look cleaner.
   6. As we save/reload the page we automatically see that the row that was in that area that had previously been too close they are now correctly formatted to not be glued to the screen success! 🙌🏿
      1. and the same thing happens down below actually in the next sections because they are all rows and they will be formatted the same.

   ## @media only screen and (max-width: 1023px) {} "small tablet to big tablet: from 768px to 1023px"

   Now lets check out this width in the browser window start with 768. This will be our tablet size. Go into tablet mode in chrome tools

   INITIAL LOOK: What appears to be wrong at this size?

   1. On the how it works page the 2 step its paragraph is not formatted right, the "us" is not under the main sentence
   2. On that same page the appe store asnd google play buttons are stacked on top of each other instead of side by side
      1. FIXED: (choose to view in tablet mode in the chrome console device tool bar and select the 768px tablet and now the buttons are side by side)
   3. We're currently in these cities page there is formatting issues with the icons and their text
   4. on the sign-up section there is formatting issues with the col on the far right
   5. Footer, the copyright is not centered

   LEC

   1. first we are going to change the over-rall font-size target body in this declaration
      1. Now it comes in very handy that we defined all the font-sizes in percentages because this means all the fonts are based on the base font size now we can just change the base to 18px instead of 20px
   2. Next lets change the padding on these sections since we are on a smaller screen
      1. target section {padding: 60px 0;} instead of 80px (my google buttons dont format correctly?)
   3. lets make the .long-copy paragrph longer because it looks weird
      1. so line-height can stay the same so we dont need to copy that over
      2. but the width can now be 80%, and therefore the left margin needs to be 10, because 10 + 10 makes 20 plus 80 makes the 100%

# Section 6: Making the webpage responsive - part 2

## @media only screen and (max-width: 1023px) {} "small tablet to big tablet: from 768px to 1023px"

### Editing the .steps-box and buttons

Let's remove some white space between the steps and the steps and the button

1.  lets target .steps-box and give it a margin-top of 10px, and then lets target .works-step and give it a margin-bottom of 40px i think the main file has it at 50px
2.  we also need to target the .steps-box:last-child and works-step:last-of-type and give steps-box:last-child a margin-top of 30px (was 10px in the video but we have different screens) and .works-steps:last-child a margin-bottom of 60px
3.  Now we will increase the app screen, it was 40% on the main file, but here we will make it 50%
4.  We also want to reduce the size of the icons because they are too big.
    1. so we target .icon-small and give it a width of 17px and a margin-right of 5px
    2. then we target .city-features and give it a font-size of 90%
    3. this didnt change much, but its the best we can get right? Let's move on

### Let's edit the prices section

We notice that these boxes are starting to look uneven lets edit them. So these boxes have a width of 90% and a margin left of 5% to center them. Let's change that

1.  these are called .plan-box
    1. lets give them a width of 100% and a margin-left of 0
    2. ok now this fixes our issue
2.  Now lets edit the font size and decrease them, lets target .plan-price
    1. give it 250%;

### Now lets edit the contact forms width

      1. lets make it 80% because we dont want it to be at its full width;

## @media only screen and (max-width: 767px) {} small phones to small tablets: from 481px tp 767px

This one is for small phones to small tablets. We have an issue here, because some of the text goes out of the actual width and creates a horizontal scroll

1. This is an easy fix to do lets start off with adding a new style to the html declaration in our main CSS file.

   1. add the style overflow-x: hidden; and now it will be hidden
   2. lets also do this for the body as well so add it under html, body {}

2. So now lets mess with the media query.

   1. Lets reduce the body font size even more to 16px \
   2. now lets target the section and give it less padding like 30px 0;
   3. now lets add the row to this and instead of our previous 0 2%; we will do 0 4%; we will do the same for .hero-text-box
   4. lets also format col and give it a width of 100% so this means they will take up 100% of their containers so they will no longer be side by side but will be stacked on top of eachother

3. Now lets fix this navigation, in fact we are going to build a mobile notification
   1. First for now, we are just going to hide all of the navigation
   2. so lets target .main-nav and give it a display of none, now this will hide the entire navigation
4. Now we want to fix the paragraph and give it a width of 100% so we need to fix the margin and kake the h1 and h2 smaller and take white space away from the cities section
   1. First lets give .long-copy a width of 100% and margin-left 0%
   2. Now, lets reduce the font size of h1 to 180% and h2 to 150%
   3. we also want to reduce the size of the .works-step and works-step:last-of-type
      1. give them both 20px to their margin-bottoms instead of 60px
   4. let's also reduce the size of the numbers and the circles
      1. copy the .works-step div and give it a width of 40px and height of 40px, margin-right 15px, padding 4px, and a font-size of 120%.
   5. Now lets target the image we want to center it .steps-box:first-child text-align center it and change the size of it too 40%
   6. Now lets target the col class from the main grid file because in this current version of the browser the columns are not aligned correctly.
      1. in the grid file the col has a margin of 1% 0 1% 1.6%;
      2. now we dont want anything of that we only want margin on the bottom
         1. rewrite as 0 0 4% 0;
         2. now this will fix the issue we had before and now we have some space here between the boxes

## @media only screen and (max-width: 480px) {} Small phones: from 0 to 480px

### editing .contact-form

1.  we want to make it 100% wide
2.  also want to remove some of the padding from between the sections cause if this is a really small phone we want to limit how much space there is

.section {
padding: 25px 0;
}
.contact-form {
width: 100%;
}
.steps-box {
margin-top: 10px;
}
.steps-box:first-child {
text-align: center;
margin-top: 5px;
}
.steps-box:last-child {
margin-top: 5px;
}
# Section 6: A note about web browsers
   ## CSS Browser Prefixes
   -CSS3 browser prefixes are a way for browser makers to add support for new CSS features in a kind of testing period. 
   Here are the CSS prefixes for different browsers:
      1. Android: -webkit-
      2. Chrome: -webkit-
      3. Firefox: -moz-
      4. Internet Explorer: -ms-
      5. iOS: -webkit-
      6. Opera: -o-
      7. Safari: -webkit-

   -here are some border-radius for different browser prefixes
   -webkit-border-radius: 25px
   -moz-border-radius: 25px
   -o-border-radius: 25px
   border-radius: 25px