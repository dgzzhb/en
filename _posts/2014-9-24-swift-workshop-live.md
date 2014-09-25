---
layout: post
title: Swift Workshop Live
category: code
---

I am attending a Swift Workshop at CMU holds by Apple and it is awesome. I will put some
of my notes here live.

Auto Layout is Super Useful! Do not forget to update frame after set it.

Each view need one view controller.

UITableView, for more details, please check API.

- It contains header, content, and footer

- You can use Reuse queue to limit resource usage

- auto completion is not only useful, but also a good way to see if something is wrong

Navigation view:

Uses Segue to transite from one scene to another

drag and release helps a ton in Xcode, much easier than Java


Dinner time: Pizza and Sliders!!!


Unwind(An-waind) Segue - pop out stack
This pops the entered textfield to the previous view.

Click Save after change some attribute in the GUI!
A friend here has a program that functions weird. We analysed from the compiler's point of
view but failed to find out why. After a while, it is because that we did not click Save..

Finally we will touch some Model! Item will be an NSObject.

No more static software, we can actually add something to the software!

I need to read more about the reuse queue thing.

If you want to turn the software off and on but keep the data, you can use NSCoder.

Something good to add:
1. text field first responder
2. make the photo smaller
3. found item details, delete items
4. Use UIDocument to properly encapsulate items in Items Manager
5. Use CloudKit for archive