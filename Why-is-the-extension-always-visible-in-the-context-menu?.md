Images can be displayed in a variety of ways on the web, including:

* using the `<img>` element
* canvas, object, video posters
* declaring in CSS


This list is not exhaustive, though the most popular and recommended way of declaring images is by using the `<img>` element. The majority of similar extensions will only work with images declared this way.

To achieve a higher success rate and offer a better user experience, Search by Image uses a different approach. The web page is parsed and images located under the clicked area are detected regardless of the method used to embed them in the page.


The difference can be tested on sites such as Instagram.

https://www.instagram.com/p/BeJmG7SnE8V/


This is the reason why the extension must be present in the context menu at all times. While the existence of an image is evident to the user before right-clicking, the extension must parse the page to detect images. It cannot know in advance if there will be an image located at the clicked area, unless web pages are preemtively parsed, even when the extension is not used. That would be an expensive and wasteful approach.


The extension can be hidden entirely from the context menu by visiting the options page, the same features are also available by using the toolbar popup instead.
