# Shopify Theme Task

## Goal:
Enhance the Shopify product page dynamically.

## Requirements:
- Modify a product page template:
  - Display Care Instructions from a product metafield (show it neatly under the description).
  - If a product has the tag `limited-edition`, show a badge ("🌟 Limited Edition!") near the product title.
  - Implement a Size Chart pop-up:
    - The size chart content should load dynamically from a JSON metafield.
  - Optimize images by using lazy loading techniques.

---

**Store address**: https://shiam-dev-02.myshopify.com/  
**Store preview Password**: `sam`

Please send a collaborator request to access the store. I will approve from my end, so you can see the admin dashboard. (No Collaborator Request Code Needed)

**For checking the task**, please visit this product only:  
https://shiam-dev-02.myshopify.com/products/trixy-halfsleeve-shirt

---

### Feature 1: Display Care Instructions from a product metafield (show it neatly under the description)

I created a product-level metafield called “Care Instructions”, with the type set to rich text. From the theme customizer, on the product template, I went to the “Product Information” section and selected a “Collapsible Row” block. Within that block, I found a pre-built rich text section provided by the theme, where I dynamically selected the metafield to display the care instructions neatly.

I also placed the product description inside a collapsible row so that all the information appears in an accordion-style layout for a cleaner presentation.


![Care Instructions](https://cdn.shopify.com/s/files/1/0708/5080/6079/files/Screenshot_2.png?v=1754374332)

**Note:** I didn’t do any coding for this feature. The feature is already available in the theme in a nice way. Instead of creating the same redundant feature, I preferred to use the theme’s existing feature. In real-world Shopify development, I first investigate whether the feature is available in the theme or not, so I don’t need to create a redundant one.

---

### Feature 2: If a product has the tag `limited-edition`, show a badge ("🌟 Limited Edition!") near the product title

I created a new block called “Badge” in the “Product Information” section and placed it under the title. I also created a `product-badge.liquid` snippet for badge rendering and logic purposes. In the “Badge” block, I added an input field to map it with product tags. This is necessary because a product can have multiple tags, but I don’t want to display all of them but only selected ones. I kept the flexibility to display multiple badges that match the block entries.

The sample input will look like this:  
`limited-edition:🌟 Limited Edition!,Bestseller:🛍️ Best Seller!`

Map product tags to custom badges. Enter each tag and badge label as `tag:label`, separated by commas.  
Example: `limited-edition:🌟 Limited Edition!, bestseller:🛒 Best Seller!`  
Matching is case-insensitive.

---

### Feature 3 and 4: Implement a Size Chart pop-up and Optimize images by using lazy loading techniques

For size chart customization, I created some block settings under the existing variant-picker block, including settings for content customization. There is one input field called `“Size Chart Mapping”` —it is used to map the variant option name where I want to display the `“Find My Size”` button. There could be other variant options like color, weight, or size. If the input field contains the value `"size"`, then the “Find My Size” button will be displayed near that variant option.

I also created a product-level metafield called `“Size Guide”`, which uses a metaobject as its value. I created a Size Guides metaobject where I can add multiple entries related to the size chart modal—for example: title, content, image, and JSON data.

I created a metaobject entry for `“Trixy Halfsleeve Shirt”` with relevant details, and under that product’s metafield, I assigned the metaobject by reference. Using this information, I displayed the size guide data in a modal popup.

Images were optimized by applying `loading="lazy"` to defer off-screen image loading and using the srcset attribute to deliver appropriately sized images based on the device's viewport. This improves performance, especially on mobile and slower networks.