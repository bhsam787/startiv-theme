# Shopify Theme Task – Product Page Enhancements

## 🛍️ Store Details

- **Store Address:** [https://shiam-dev-02.myshopify.com/](https://shiam-dev-02.myshopify.com/)
- **Store Preview Password:** `sam`

👉 **For checking the task, please visit this product only:**  
[https://shiam-dev-02.myshopify.com/products/trixy-halfsleeve-shirt](https://shiam-dev-02.myshopify.com/products/trixy-halfsleeve-shirt)

---

## 🎯 Goal

Enhance the Shopify product page dynamically.

---

## ✅ Requirements

- Modify a product page template
- Display **Care Instructions** from a product metafield (show it neatly under the description)
- If a product has the tag `limited-edition`, show a badge (**"🌟 Limited Edition!"**) near the product title
- Implement a **Size Chart pop-up**
  - The size chart content should load dynamically from a **JSON metafield**
- Optimize images by using **lazy loading techniques**

---

## 📌 Features

### 🔹 Feature 1: Display Care Instructions from a Product Metafield (Show It Neatly Under the Description)

I created a product-level metafield called **“Care Instructions”**, with the type set to **rich text**. From the **theme customizer**, on the **product template**, I went to the **“Product Information”** section and selected a **“Collapsible Row”** block.

Within that block, I found a pre-built **rich text** section provided by the theme, where I dynamically selected the metafield to display the care instructions neatly.  
I also placed the **product description** inside a collapsible row so that all the information appears in an accordion-style layout for a cleaner presentation.

**Note:** I didn’t do any coding for this feature. The feature is already available in the theme in a nice way. Instead of creating the same redundant feature, I preferred to use the theme’s existing feature.  
In real-world Shopify development, I first investigate whether the feature is available in the theme or not, so I don’t need to create a redundant one.

---

### 🔹 Feature 2: If a Product Has the Tag `limited-edition`, Show a Badge ("🌟 Limited Edition!") Near the Product Title

I created a new block called **“Badge”** in the **“Product Information”** section and placed it under the **title**. I also created a **`product-badge.liquid`** snippet for badge rendering and logic purposes.

In the **Badge** block, I added an **input field** to map it with **product tags**. This is necessary because a product can have multiple tags, but I don’t want to display all of them — only selected ones. I kept the flexibility to display multiple badges that match the block entries.

### 📝 Sample Input

```
limited-edition:🌟 Limited Edition!,Bestseller:🛍️ Best Seller!
```

Map product tags to custom badges.  
Enter each tag and badge label as `tag:label`, separated by commas.  
**Example:**

```
limited-edition:🌟 Limited Edition!, bestseller:🛒 Best Seller!
```

**Note:** Matching is case-insensitive.

---

### 🔹 Feature 3 & 4: Implement a Size Chart Pop-up and Optimize Images Using Lazy Loading Techniques

#### 🧩 Size Chart Pop-Up

For size chart customization, I created some **block settings** under the existing **variant-picker** block, including settings for content customization.

There is one input field called **“Size Chart Mapping”** — it is used to map the **variant option name** where I want to display the **“Find My Size”** button. There could be other variant options like **color**, **weight**, or **size**.  
If the input field contains the value `"size"`, then the **“Find My Size”** button will be displayed near that variant option.

I also created a **product-level metafield** called **“Size Guide”**, which uses a **metaobject** as its value. I created a **Size Guides metaobject** where I can put multiple entries related to the size chart modal, for example:

- Title
- Content
- Image
- JSON data

I created a **metaobject entry** for **“Trixy Halfsleeve Shirt”** with some details, and under that product’s metafield, I assigned the metaobject by reference.  
From this information, I displayed the size guide data over the **modal popup**.

#### 🖼️ Image Optimization (Lazy Loading)

All images on the product page have been optimized using **lazy loading techniques**, leveraging the native `loading="lazy"` attribute.  
This ensures faster load times and a better user experience by only loading images when they enter the viewport.

---

## 🔐 Access Instructions

Please send a **collaborator request** to access the store:  
👉 [https://shiam-dev-02.myshopify.com/](https://shiam-dev-02.myshopify.com/)

I will approve the request from my end, so you can view the admin dashboard.  
**No collaborator request code is needed.**

---

## 📁 Files & Configuration Summary

| Item                      | Description                                                  |
|---------------------------|--------------------------------------------------------------|
| `product-badge.liquid`    | Snippet used for rendering badges based on product tags      |
| Collapsible Row Block     | Used to display description and care instructions neatly     |
| Badge Block               | Created under title to dynamically show product badges       |
| Variant Picker Block      | Enhanced with size chart mapping field                       |
| Metaobject: Size Guides   | Contains size chart content (title, image, content, JSON)    |
| Metafields:               | `care_instructions` (richtext), `size_guide` (metaobject)    |

---

## ✅ Summary

This task demonstrates a clean, dynamic enhancement of the Shopify product page using:

- **Native theme functionalities** where available
- **Custom snippets** only where necessary
- **Metafields and metaobjects** for scalable content management
- **Performance optimization** with image lazy loading

---

## 👨‍💻 Developer Notes

- All work was done with scalability and reusability in mind.
- Features were added in a way that avoids redundant coding.
- Admin configuration was prioritized to empower non-developers to manage the content.

---

## 📅 Date

**August 2025**