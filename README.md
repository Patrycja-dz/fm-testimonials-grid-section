# Frontend Mentor - Testimonials grid section solution

This is a solution to the [Testimonials grid section challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/testimonials-grid-section-Nnw6J7Un7). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size

### Links

- Solution URL: [solution URL](https://github.com/Patrycja-dz/fm-testimonials-grid-section)
- Live Site URL: [live site ](https://patrycja-dz.github.io/fm-testimonials-grid-section/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- CSS Animations & Transitions

### What I learned

This project was a great opportunity to practice and solidify several front-end concepts. Here are some key takeaways:

1.  **CSS Custom Properties for Theming and Consistency:**
    I extensively used CSS custom properties (variables) to manage colors, font families, font sizes, and spacing. This made it easy to maintain a consistent design system and would simplify future theming or adjustments.

    ```css
    :root {
      /* Colors */
      --color-purple-500: hsl(263, 55%, 52%);
      --color-grey-500: hsl(217, 19%, 35%);
      /* Typography */
      --font-family-main: "Barlow Semi Condensed", sans-serif;
      /* Spacing */
      --space-400: 32px;
    }

    .testimonial {
      background-color: var(--color-purple-500);
      padding: var(--space-400);
    }
    ```

2.  **Responsive Layout with CSS Grid:**
    CSS Grid was crucial for creating the main layout of the testimonials. I used it to arrange the cards and make the layout responsive. The `grid-template-columns` property with `repeat()` and `fr` units, along with media queries, allowed for a flexible and adaptive design. Spanning items across columns (e.g., `grid-column: span 2;`) was also a key technique.

    ```css
    /* From styles.css */
    .testimonials-grid {
      display: grid;
      width: min(95%, 70rem);
      column-gap: var(--space-400);
      row-gap: var(--space-300);
    }

    @media (min-width: 50em) {
      .testimonials-grid {
        grid-template-columns: repeat(4, 1fr);
      }
      .testimonial-grid-col-span-2 {
        grid-column: span 2;
      }
      .testimonial:last-child {
        grid-column: 4;
        grid-row: 1 / span 2;
      }
    }
    ```

3.  **Mobile-First Approach:**
    The styling was approached with a mobile-first mindset, defining base styles for smaller screens and then using media queries (`@media (min-width: 50em)`) to apply adjustments for larger screens. This ensures a good user experience across all device sizes.

4.  **Subtle Animations and Transitions for Better UX:**
    I added hover effects and a fade-in entrance animation to the testimonial cards using CSS transitions and keyframe animations. This provides visual feedback and makes the interface feel more interactive.

    ```css
    @keyframes fadeInSlideUp {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .testimonial {
      transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
      animation: fadeInSlideUp 0.5s ease-out forwards;
      opacity: 0; /* Initial state for animation */
    }

    .testimonial:hover {
      transform: translateY(-5px) scale(1.02);
      box-shadow: 0px 8px 15px 0px rgba(0, 0, 0, 0.3);
    }
    ```

    Staggering animations with `animation-delay` for different children also enhances the visual appeal on load.

5.  **Semantic HTML for Accessibility and SEO:**
    Using appropriate HTML5 tags like `<main>`, `<article>`, `<h2>`, `<blockquote>`, and providing descriptive `alt` text for images helps improve accessibility and SEO.

6.  **CSS Reset for Cross-Browser Consistency:**
    Employing a CSS reset helps in neutralizing default browser styles, providing a more consistent base to build upon.

### Continued development

- **Advanced CSS Grid/Flexbox Techniques:** Explore more complex layouts and alignment options.
- **Accessibility (A11y) Enhancements:** Conduct a more thorough accessibility audit, potentially adding ARIA attributes where beneficial.
- **JavaScript for Interactivity:** For future projects, consider adding JavaScript for more dynamic interactions if the design requires it (though CSS was sufficient here).
- **Performance Optimization:** Look into optimizing images further or exploring techniques like critical CSS for larger projects.

### Useful resources

- [MDN Web Docs](https://developer.mozilla.org/) - An indispensable resource for HTML, CSS, and JavaScript.
- [CSS-Tricks: A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) - For in-depth understanding of CSS Grid.
