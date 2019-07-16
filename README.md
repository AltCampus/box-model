# Box Model

## Topics of the day

1. Display Properties
2. Block Vs Inline Vs Inline-Block
3. Box Model
4. Width
5. Height
6. Padding
7. Border
8. Margin
9. Table of comparison between block, inline, and inline-block.
10. Calculating the width and height of an element.
11. Developer Tools

Till now we have seen how HTML & CSS work together. We know now how the HTML work and what are the basic fundamental of HTML such as elements, tags, attributes. We also know how to use different elements for different contents. We have also seen how CSS works and how to target any element in the HTML document in CSS and style them according to the need.
Now its time to go a bit deeper about the different elements and see how they behave once it comes to browser. We will see how elements are displayed and what will be its size in a page. During the discussion, we will get know about the box model of an element. We will also come to know about the different properties and values of CSS in our discussion.
Before we directly jump to box model we will start with display properties of an element.

## 1. Display properties

From the earlier discussion, we know that by default there are two types elements, block-level elements, and inline-level elements. We have seen the difference between them. We also covered block-level elements always starts from a new line and takes the available width and inline-level elements take the space as much as it requires according to the content and lines up one after the other.
In an HTML document, the block-level or the inline-level elements or something else, are all determined by the display property. Therefore, every element has a default display property value. It can be block, inline, inline-block, and none. There are a few more which we will discuss later on, for now, let's cover all these four display property values.
As we all know we can overwrite any property values in CSS, in a similar way we can also overwrite the default display property values. It means we can make block to inline or inline-block and inline to block or inline-block etc. Let's see how we can do this.

## 2. Block Vs Inline Vs Inline-Block

### Block

A block level elements accept all the box-model(which we will discuss soon) properties and values. To convert any element into a block level element we just need to change its display property.

```
  span {
    display: block;
  }
```

By default, span is inline-level elements but now as we have changed its display property now it will behave like a block level elements and it will accept all the box-model properties and values.

### Inline

To make any element behave like inline-level elements we can change its display properties.

```
  p {
    display: inline;
  }
```

By default, p is a block-level element but now it will behave like an inline-level element because we have overwritten its display property.

### Inline-block

An inline-level element does not accept all the box-model properties and values. So we have another display property value i.e. inline-block.

```
  p {
    display: inline-block;
  }
```

With the inline-block value we can make the element behave like inline level, means the element will take the space according to the content and will line up one after one instead of taking whole available width and starting from a new line. But at the same time, it will also accept all the box-model properties like block level elements.

### Removing Space between the inline-block elements.

It is perfect to make the elements inline-block whenever we will need to make the elements sit one after another and also define all the box-model properties. But there is some problem with inline-block elements. Inline-block elements are not always touching whenever they come one after one. You'll always find a small space between the inline-block elements. And that default small space between the inline-block elements may disturb the flow of content. There are different ways to get rid of those small space. Let's try a few of them:
One we can set the parent's(containing inline-block elements) font-size to 0. But here again, we will have to set the font-size for children according to the need.

```
  <div class="parent">
    <div class="inline-block>.......</div>
    <div class="inline-block>.......</div>
    <div class="inline-block>.......</div>
  </div>

  .parent {
    font-size: 0;
  }
  .inline-block {
    display: inline-block;
  }
```

The other two ways can be applied in HTML to remove space. One we can place the opening tag of each new inline-block element just after the closing tag of the previous inline-block element.

```
  <div class="inline-block>
    .......
  </div><div class="inline-block>
    .......
  </div><div class="inline-block>
    .......
  </div>
```

And the last way is to open HTML comment just after the closing tag of an inline-block element and then close the HTML comment just before the opening tag of next inline-block element.

```
<div class="inline-block>
    .......
</div><!--
--><div class="inline-block>
    .......
</div><!--
--><div class="inline-block>
    .......
</div>
```

It is a personal choice which way we should choose, it is entirely on you. All options will work fine.

### None

```
  p {
    display: none;
  }
```

To hide any element from the page we can set its display property value 'none'. So when the page will render the element will be hidden as if that element does not exist in the HTML document.

We have been listening about the box-model properties and values from the beginning. So let's begin our discussion on the box-model.

## 3. Box Model

According to the box model, every element is a rectangular box in a page and it may have some width, height, padding, borders, and margins. The width, height, padding, borders, and margins are the key points of the box model, which plays an important role in deciding the size of a box on a page.
It is important to note here that every element is a rectangular box in a page and every element has to comply with the rules of the box model. The core of the box defined by the width and height of the box, that depends on the display property of the element, contents of the element or specified width and height of the element in CSS. After the width and height, padding comes followed by borders, which again increase the size of the box outward. And at the last margin comes which is getting applied outside the box.
Let's discuss all these box model properties(width, height, padding, borders, and margins) one by one and then after we will learn how to calculate the total width(actual space taken by the element horizontally) and total height(actual space taken by the element vertically).

## 4. Width

Every element has some default width based on the display property. If it is a block-level element it will have 100% width covering whole horizontal space. If it is an inline or inline-block element it will have width according to the content it wraps.
To set a specified width to an element we can use the width property:

```
  div {
    width: 300px;
  }
```

One important thing you must note here that you cannot set a fixed width of an inline-level element. So if you try to specify a width to an inline element it won't accept.

## 5. Height

As every element has some default width in a similar way every element also has some default height and that is always determined by its content. Similarly width, height also cannot be fixed for the inline-level elements. So to specify the height of non-inline elements we can use the height property:

```
  div {
    height: 300px;
  }
```

## 6. Padding

Padding comes after width and height and falls inside the element's border. Here is how the padding property is applied.

```
  div {
    padding: 20px;
  }
```

The padding property is applied to provide space around the content, within an element . Sometimes it is also called breathing space around the content inside the element.
In the above code `20px` of padding has been applied therefore there will be a space of 20px around the content in the box.
For the block and inline-block elements, padding works normally. But when it comes to applying padding for inline-level elements, it works a bit differently. The vertical padding( top and bottom) may blend into the line of above and below elements but will be displayed. The left and right padding will work normally.

### Padding Declarations

There are different ways to apply padding in an element. We have shorthand as well as longhand properties for padding in CSS.

#### Shorthand

```
  div {
    padding: 20px;
  }
```

This is the shorthand property to apply padding on all the four sides of the element.

```
div {
  padding: 20px 40px;
}
```

This is another shorthand property to apply padding. The first value is for the top and bottom padding and the last value is for left and right padding.

To set unique values for individual side padding we can define something like this

```
div {
  padding: 10px 0 20px 30px;
}
```

This will be applied on the all the four sides with individual value. It goes clockwise. The first value is for top padding, second is for right, the third value is for the bottom and the last value is left padding of the element.

#### Longhand

In the longhand properties, we can set value for one side at a time.

```
  div {
    padding-top: 10px;
    padding-right: 0;
    padding-bottom: 20px;
    padding-left: 30px;
  }
```

## 7. Border

After padding and before the border comes. The border is to provide some outline around an element. To apply border we have border property which requires three different values: `border-width, border-style, and border-color`.

```
div {
	border: 10px solid red;
}
```

The above border property has shorthand values which will provide a `10px` border of red color around the element on all the four sides. In the longhand, we can apply all the above values individually.

```
  div {
    border-width: 10px;
    border-style: solid;
    border-color: red;
  }
```

To apply border on the individual side we can say define individually like, `border-top, border-right, border-bottom, and border-left`.

```
  div {
    border-bottom: 10px solid #272727;
  }
```

Again here this is shorthand values for the border-bottom property. In the longhand values we can say something like this:

```
  div {
    border-bottom-width: 10px;
    border-bottom-style: solid;
    border-bottom-color: #272727;
  }
```

The width and color of the border are the normal things and can be applied normally, that we have already seen how to use the units and colors in CSS. But for the border, we have different styles. The most common styles are solid, double, dashed, dotted and none. Based on these styles we can have different appearances for the border.

### Border Radius

There is another property for the border is `border-radius`. With the help this property we can get a rounded or soft corner of the border. And the values can be in normal length units like pixels and percentage.

```
  div {
    border-radius: 6px;
  }
```

## 8. Margin

The last property in the box model is the margin. The margin property is very similar to padding. But space instead of applying inside the element it is being applied outside the element. To apply margin we have margin property:

```
  div {
    margin: 20px;
  }
```

Margin property is applied to provide a gap between the elements in a page. It provides space around the element. So from the above code, there will be space of 20px around the element. It can be also used to position the element in the page.

### Margins on block elements

One of the common behavior in the box model is that the vertical margin collapses between two block level elements. It's better to take an example to make it clear. Suppose we have two paragraph element and by default, p is block level element. Now let's apply a margin to both paragraph element.

```
  <p>.........</p>
  <p>.........</p>

  p {
    margin: 20px;
  }
```

Normally both the paragraph elements will be having a margin of 20px all around it. But the vertical margin between the elements will be also 20px only. Ideally, it should be 40px, 20px bottom margin of the first paragraph element and 20px top margin of the second paragraph element. This is known as collapsing of a vertical margin between the block elements. Sometimes we can see something like this also

```
  <p class="para1">.........</p>
  <p class="para2">.........</p>
  .para1 {
    margin-bottom: 30px;
  }
  .para2 {
    margin-top: 70px;
  }
```

Ideally, the vertical margin between the para1 and para2 should be 100px, but it will be 70px. Because smaller margin always gets collapsed into the bigger one.

### Margins on inline elements

When it comes to applying margin on inline elements, we have something different behavior than the block elements. In inline elements, the horizontal margin works normally. You will see left and right margin working normally on inline elements. But the vertical margins are ignored on inline elements.

### Margin Declarations

Margin declarations are exactly similar to padding. Whatever ways we have seen to declare padding similarly we have the same ways to declare margin.

#### Shorthand

```
  div {
    margin: 20px;
  }
  div {
    margin: 10px 20px;
  }
  div {
    margin: 0 10px 15px 20px;
  }
```

#### Longhand

```
  div {
    margin-top: 0;
    margin-right: 10px;
    margin-bottom: 15px;
    margin-left: 20px;
  }
```

We covered almost all the topics of box model. Now based on that let's calculate the exact size of an element.

## 10. Calculating the width and height of an element.

We have seen how to apply width, height, padding, borders, and margins. Now we also know that these properties are basic building blocks of the box model. Let's put them together to create a box and see what is the exact size of the box. To create a box, we will take a block level element so that we can apply all the box model properties normally without any disturbances. For example, let's take a div element.

```
  div {
    width: 300px;
    height: 200px;
    padding: 20px;
    border: 8px solid #272727;
    margin: 20px;
  }
```

If you open the div in your browser you'll find the div is taking total space of `396px` in the horizontal direction and `296px` in the vertical direction. To see this we will learn about the developer tool in the next section. In the developer tool, we will see the exact box model of any element. But before that let's see how the width and height become `396px and 296px` respectively. Let's see how the total width and height is being calculated according to the box model.

#### Total width:

```
  marging-left + border-left + padding-left + width + padding-right + border-right + margin-right
```

So, according to the above formula, we have a total width of the div:

```
  396px = 20px +8px + 20px + 300px + 20px + 8px + 20px
```

#### Total Height:

```
  marging-top + border-top + padding-top + width + padding-bottom + border-bottom + margin-bottom
```

So, according to the above formula, we have a total height of the div:

```
  296px = 20px +8px + 20px + 200px + 20px + 8px + 20px
```

This is how the default box model works for any element in a page. By default, each and every property is additive in the box model to calculate the exact width and height of an element.
The box model is one of the most confusing topics in HTML and CSS. You might have seen just now how the width and height of the element changed. But, this is one of the most important topics also in HTML and CSS. Because here you get to know how elements behave what will be exact space it will be taking when it comes to the browser. Based on this topic only every element in a page behaves. Once you have clarity on this topic rest of the topic will be easy for you to pick up.

## 11. Developer Tools

Most of the browsers come with a Developer Tools to inspect element in a page. It helps us to see all the CSS properties that have been applied on an element also it let us know where the element is sitting in the HTML document.
To open a Developer Tools you can right click on the page in a browser you will see an option to inspect. Once you click the inspect option you will find a new window open below your browser. On the left side, you will see all the HTML code used to create the page and on the top left corner of the window, you will also get a button to select any element on the page.
After clicking that button you can select any element on the page by clicking on it. Once you select an element on the page on the right side you will find all the CSS styles defined for the selected element. On the right-hand side, you will also see a few tabs within Developer Tools. If you select 'computed' a break down of the box model will open of the selected element.
This is known as the real box model of an element on a page. Here you will find all box model properties(width, height, padding, borders, and margins) defined for the element. This box model defines the exact size of the box on a page.
The Developer tools are one most frequently used tool by the developer. There are a lot more things can be done in developer tools. Slowly and gradually we will get to know about those things.

## Answer the following questions

1. Why do we need to learn the box model?
2. What are the different display properties?
3. What are the different box model properties?
4. How to calculate the exact width and height of an element?

## Do the exercise1

## Additional Resources

1. https://learn.shayhowe.com/html-css/opening-the-box-model/

- https://internetingishard.com/html-and-css/css-box-model/
