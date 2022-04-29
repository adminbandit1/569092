Images can be displayed in a variety of ways on the web, including:

- using the `<img>` element
- canvas, object, video posters
- declaring in CSS

This list is not exhaustive, though the most popular way of displaying images is by using the `<img>` element. The majority of similar extensions will only work with images embedded this way.

To achieve a higher success rate and offer a better user experience, Search by Image uses a different approach. The web page is parsed and images located at the selected area are detected regardless of how they were embedded in the page.

The difference can be tested on sites such as Instagram: https://www.instagram.com/p/BeJmG7SnE8V/

This is the reason why the extension must be present in the context menu at all times. While the existence of an image is evident to the user before right-clicking, the extension must parse the page to detect images. It cannot know in advance if there will be an image located at the selected area, unless web pages are preemptively parsed even when the extension is not used, which would impact browser performance.

The extension can be hidden entirely from the context menu by visiting the options page, the same features are also available from the toolbar popup.