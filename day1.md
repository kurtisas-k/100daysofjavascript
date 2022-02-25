# 2/24/2022

In a Vue3 project one of the things that always messed with me was how to get information to a child componenet, and then form the child component to the parent. 

The pattern suggested was using props to send messages, and then emiting messages and events based on what happens with the child component.

This was intuitive enough. What I couldn't understand was how this would apply to objects where I have to get more data. 

For example I get a list of lists at the page level (parent). Each of those lists has a subsequent ID so I then enumerate through the lists, which will give me ids for actions (edit, delete), as well as pass the list itself to a ListView.vue type component.

So if I have a page: Page.vue and it contains a ListsView, then I would pass all those lists to the ListsView, and then from the ListsView pass the series of lists individually into their ListView. 

The page is still messing with me a bit. Is a page just a component? And if I have two layers of children, say the page is Dad, the ListsView is son, then the ListView is the grandson, then does an emit chain up to the Dad, or does it just go to the son? Not a big deal if we have to pass the messages along - but I'm assuming it should bubble up?

Anyways the point is it helps to thing this way for building components. ListsView > ListView > TermView kind of thing. Little threads of responsibility. And it makes it easier to locate things like, "Where are my data methods located?" 
