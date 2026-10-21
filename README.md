# Makao Interiors🏠


# Makao Interiors

**Thoughtful spaces. Inspired living.**

Makao Interiors is a responsive interior design portfolio and enquiry website built with **React, Vite, and plain CSS**.

The project provides a customisable website foundation for an interior designer or studio. Visitors can explore design concepts, learn about services, and prepare a consultation enquiry through email or WhatsApp.

> **Project status:** A functional portfolio demonstration. Sample concepts, stock photographs, business information, and consultation policies must be replaced or approved before use by a real business.

---

## Project Purpose

Interior designers need a clear way to present their style, explain their services, and help prospective clients start a conversation.

Makao Interiors brings these activities into one website through:

- A visual introduction to the business.
- Editable service information.
- Searchable and filterable project concepts.
- Detailed project views.
- A guided consultation enquiry form.
- Email and WhatsApp contact options.

The intended visitor journey is:

**Explore concepts → understand services → describe a project → contact the designer → discuss a proposal.**

---

## Features

### Responsive Navigation

- Desktop navigation and a mobile menu.
- Active navigation indicators based on the current section.
- Mobile menu closes after selecting a link.
- Support for closing the menu with Escape or an outside click.

### Home and About Sections

- Large hero photograph and introductory headline.
- Links to projects and consultation enquiries.
- Business introduction and design values.
- Editable content for a future designer or studio.

### Services

The current sample services include:

- Residential interiors.
- Commercial spaces.
- Styling and decoration.
- Space planning.

Selecting **Request a quotation** scrolls to the enquiry form and automatically selects the corresponding service.

### Project Gallery

- Category filters: All, Residential, Commercial, and Styling.
- Text search across project names, categories, descriptions, and concepts.
- A count of matching results.
- An empty-results message with a reset option.
- Project details displayed in a modal dialog.
- Previous and Next controls for browsing matching concepts.
- Image loading placeholders and retry controls inside the viewer.
- A **Discuss a similar project** action that selects the related enquiry service.

### Consultation Enquiries

The form collects:

- Name.
- Email address or phone number.
- Project location.
- Service required.
- Optional estimated budget in KES.
- Project description.

It includes:

- Client-side validation.
- Field-specific error messages.
- Focus on the first invalid field.
- A project description character counter.
- Automatic service selection from service cards and project concepts.
- Preservation of other form entries when the selected service changes.

### Contact Options

- Email draft preparation using `mailto:`.
- WhatsApp messages containing the enquiry details.
- A floating WhatsApp link when a valid number is configured.
- Contact options hidden when their receiving details are not configured.

### Additional Interface Features

- Frequently asked questions.
- Back to top button.
- Custom SVG favicon.
- Page description and basic social sharing metadata.
- Reduced-motion styling.
- Keyboard focus indicators and labelled form controls.

---

## Technology Stack

| Technology | Purpose |
| --- | --- |
| React | Component-based interface and application state |
| Vite | Development server and production build |
| JavaScript | Filtering, validation, navigation, and enquiry behaviour |
| CSS | Layout, responsive styling, and visual presentation |
| HTML | Document structure and metadata |
| Google Fonts | DM Sans and Playfair Display typography |
| Unsplash | Stock photography used in the demonstration |

The current version uses a single-page layout with section links. It does not require a database or visitor accounts.

---

## Project Structure

```text
makao-interiors/
├── public/
│   └── favicon.svg
├── src/
│   ├── components/
│   │   ├── BackToTop.jsx
│   │   ├── EnquiryForm.jsx
│   │   ├── FAQ.jsx
│   │   ├── Footer.jsx
│   │   ├── Hero.jsx
│   │   ├── Navbar.jsx
│   │   ├── ProjectGallery.jsx
│   │   ├── ProjectImage.jsx
│   │   ├── ServiceCard.jsx
│   │   ├── ServicesSection.jsx
│   │   └── WhatsAppButton.jsx
│   ├── data/
│   │   └── business.js
│   ├── App.jsx
│   ├── main.jsx
│   └── styles.css
├── index.html
├── package.json
├── package-lock.json
└── README.md
```

Vite configuration and other scaffold files may also be present.

---

## Getting Started

### Prerequisites

Install:

- A Node.js version compatible with the Vite version in `package.json`.
- npm.
- Git, if cloning the repository.

Check your installation:

```bash
node --version
npm --version
```

### Installation

Clone this repository using its GitHub clone URL:

```bash
git clone <repository-url>
```

Open the downloaded project folder:

```bash
cd <project-folder>
```

Install dependencies:

```bash
npm install
```

### Start the Development Server

```bash
npm run dev
```

Open the local URL printed in the terminal.

### Create a Production Build

```bash
npm run build
```

The build output is generated in:

```text
dist/
```

### Preview the Production Build

```bash
npm run preview
```

Open the preview URL printed in the terminal.

This command previews the built website locally; it does not publish it online.

---

## Available Commands

| Command | Description |
| --- | --- |
| `npm install` | Install project dependencies |
| `npm run dev` | Start the development server |
| `npm run build` | Generate the production build |
| `npm run preview` | Preview the production build locally |

---

## Business Configuration

Edit:

```text
src/data/business.js
```

The file exports four sets of information:

```js
export const business = {
  // Business and contact information
};

export const services = [
  // Services displayed on the website
];

export const projects = [
  // Gallery concepts and project descriptions
];

export const faqs = [
  // Frequently asked questions
];
```

Keep all four exports because the website components depend on them.

### Contact Details

Update the `business` object:

```js
export const business = {
  name: "Makao Interiors",
  tagline: "Thoughtful spaces. Inspired living.",
  email: "",
  whatsapp: "",
  phone: "",
  serviceArea: "Your approved service areas",
};
```

- `email`: The receiving business email.
- `whatsapp`: The receiving WhatsApp number in international format, using digits only.
- `phone`: The phone number as it should appear to visitors.
- `serviceArea`: The locations actually served by the business.

For Kenyan WhatsApp numbers, use the country code `254` in place of the initial `0`.

The current browser-based contact features do not require environment variables or API credentials.

Do not place passwords, private API keys, or other secrets in this file.

### Branding

Some branding and introductory text also appears in:

- `Navbar.jsx`
- `Hero.jsx`
- `Footer.jsx`
- `App.jsx`
- `index.html`

Review these files when adapting the project for another business.

### Colours and Typography

The main theme variables are defined in `src/styles.css`:

```css
:root {
  --cream: #fcfaf6;
  --sand: #f0ebe2;
  --olive: #444e3e;
  --dark: #292c27;
  --muted: #68685f;
  --line: #dedbd2;
  --gold: #957147;
}
```

Update these values to match the buyer’s approved brand.

Fonts currently load from Google Fonts, and photographs load from external URLs. These assets require network access unless replaced with locally hosted files.

---

## Managing Projects

Each gallery item follows this structure:

```js
{
  id: "unique-project-id",
  title: "Project title",
  category: "Residential",
  subtitle: "A short description",
  image: "/images/project-photo.jpg",
  alt: "An accurate description of the photograph",
  brief: "The project requirements or concept brief.",
  solution: "The design approach or proposed solution."
}
```

### Project Guidelines

- Give each project a unique `id`.
- Use accurate alternative text.
- Compress photographs before publishing.
- Obtain permission to publish client work and identifying details.
- Keep concept projects clearly identified.
- Avoid presenting stock photographs as completed client work.

To use local photographs, create:

```text
public/images/
```

Then reference an image as:

```js
image: "/images/project-photo.jpg"
```

### Categories and Service Selection

Category filters and their related services are configured in:

```text
src/components/ProjectGallery.jsx
```

If you rename categories or services, update both the filters and the `categoryServices` mapping so project enquiries select the correct service.

---

## How Enquiries Work

### Email

The form opens the visitor’s configured email application with a prepared subject and message.

The visitor must review the draft and press **Send** in their email application.

### WhatsApp

The form opens WhatsApp with a prepared message containing the project details.

The visitor must review the message and press **Send** in WhatsApp.

### Important Limitations

- The website does not send enquiries through a backend.
- It does not store form entries in a database.
- It cannot confirm that an email or WhatsApp message was delivered.
- Email behaviour depends on the visitor’s device and email setup.
- Browser settings may prevent a WhatsApp tab from opening.
- Form entries are not persisted after a page refresh.
- Client-side validation improves usability but is not a substitute for server-side validation if a backend is added.

Direct form submission, delivery tracking, spam protection, and enquiry storage require additional implementation.

---

## Accessibility

The interface includes:

- A skip-to-content link.
- Semantic sections and heading structure.
- Labels for form controls.
- Field-level validation messages.
- Visible keyboard focus.
- Native dialog behaviour for project details.
- Focus restoration after closing a project viewer.
- Reduced-motion support.

These features should be checked again after changing content, colours, or components. This README does not claim a formal accessibility audit.

---

## Photography and Content

The demonstration uses stock images from Unsplash:

- https://images.unsplash.com/photo-1600210492486-724fe5c67fb0
- https://images.unsplash.com/photo-1600607687920-4e2a09cf159d
- https://images.unsplash.com/photo-1497366811353-6870744d04b2

Review the applicable terms and any additional permissions before commercial use:

https://unsplash.com/license

Image licensing is separate from the licensing of this repository’s source code.

The sample projects, business introduction, service offering, and FAQ answers require review before being published as a real designer’s business content.

---

## Search and Sharing

The supplied demonstration includes:

```html
<meta name="robots" content="noindex, nofollow" />
```

Keep this directive while the website is a demonstration.

For an approved public launch:

- Update the page title and description.
- Add the final website URL and an approved social sharing image.
- Replace sample business information.
- Remove `noindex` when the website is ready for indexing.
- Add an appropriate production sitemap and robots.txt.

The `noindex` directive is not password protection and does not make a deployed website private.

---

## Deployment

The production output is a static website in the `dist` directory.

For a compatible static hosting provider, configure:

| Setting | Value |
| --- | --- |
| Project root | Folder containing `package.json` |
| Build command | `npm run build` |
| Output directory | `dist` |

The current website uses section links such as `#projects` and `#contact`, rather than separate page routes.

After deployment, verify the website on a phone and desktop, including its images, navigation, project viewer, and contact links.

---

## Verification Checklist

### Interface

- [ ] Desktop and mobile navigation work.
- [ ] Navigation links scroll to the expected sections.
- [ ] Active navigation indicators update.
- [ ] No unwanted horizontal scrolling appears.
- [ ] Back to top works.

### Projects

- [ ] Category filters work.
- [ ] Search returns the expected concepts.
- [ ] Empty search results can be reset.
- [ ] Project details open and close.
- [ ] Escape closes the viewer.
- [ ] Previous and Next follow the matching results.
- [ ] Failed viewer images offer a retry option.
- [ ] Project enquiries select the correct service.

### Enquiries

- [ ] Required fields reject invalid entries.
- [ ] Error messages identify the affected fields.
- [ ] Selecting another service preserves other entries.
- [ ] Email drafts contain the correct information.
- [ ] WhatsApp opens the correct receiving number.
- [ ] WhatsApp messages contain the project details.
- [ ] The interface does not claim confirmed delivery.

### Launch Readiness

- [ ] The production build succeeds.
- [ ] Real contact details are configured and tested.
- [ ] The designer approves the business content.
- [ ] Photographs have suitable permissions.
- [ ] Concept work is clearly identified.
- [ ] Consultation policies and service areas are accurate.
- [ ] Privacy wording matches the final enquiry workflow.
- [ ] Domain, hosting, ownership, and maintenance are agreed.

---

## Possible Future Improvements

These features are outside the current implementation:

- Direct enquiry submission through a backend.
- Email notifications and spam protection.
- A content management system.
- Separate project pages.
- Multiple photographs per project.
- Genuine before-and-after comparisons.
- Consultation scheduling.
- An administration dashboard.
- Analytics configured for the business’s needs.

---

## Author

**Johnstone Oroni**

Built as a practical React project and a customisable website foundation for interior design businesses.

---

## Licence

A source-code licence has not been specified in this README.

Add a `LICENSE` file defining the intended permissions before distributing the project as a reusable template. Third-party photographs, fonts, and other assets remain subject to their own terms.
