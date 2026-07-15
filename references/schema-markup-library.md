# All-Star Renovations — Complete JSON-LD Schema Markup Library (2026 AEO + Voice Optimized)

This library contains production-ready JSON-LD snippets optimized for:
- Google AI Overviews
- Voice Search Assistants
- Featured Snippets
- Local Pack + Maps
- Answer Engine Citation (ChatGPT, Perplexity, Gemini, etc.)

**Implementation Notes**:
- Place `<script type="application/ld+json">` in the `<head>` of every page.
- Use one main schema per page + layered supporting schemas (FAQPage, Service, etc.).
- Keep NAP consistent: "All-Star Renovations", "11 Arnett Ln, Conway, AR 72032", "(501) 504-3398".
- Update `dateModified` and author fields regularly.

---

## 1. LocalBusiness Schema (Homepage + Footer on all pages)

```json
{
  "@context": "https://schema.org",
  "@type": "HomeAndConstructionBusiness",
  "name": "All-Star Renovations",
  "alternateName": "All-Star Shower Systems",
  "description": "Expert bathroom remodeling contractor in Conway, AR specializing in All-Star Shower Systems, walk-in showers, tub-to-shower conversions, and Aging Safely Walk-In Tubs. 2-day installs with lifetime material warranties.",
  "url": "https://allstarreno.com",
  "telephone": "(501) 504-3398",
  "email": "info@allstarreno.com",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "11 Arnett Ln",
    "addressLocality": "Conway",
    "addressRegion": "AR",
    "postalCode": "72032",
    "addressCountry": "US"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "35.0887",
    "longitude": "-92.4421"
  },
  "areaServed": [
    {"@type": "City", "name": "Conway"},
    {"@type": "City", "name": "Greenbrier"},
    {"@type": "City", "name": "Vilonia"},
    {"@type": "City", "name": "Maumelle"},
    {"@type": "City", "name": "Cabot"},
    {"@type": "City", "name": "Sherwood"},
    {"@type": "City", "name": "Little Rock"}
  ],
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "07:30",
      "closes": "17:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Saturday",
      "opens": "07:00",
      "closes": "19:00"
    }
  ],
  "priceRange": "$$-$$$",
  "image": "https://allstarreno.com/images/hero-bathroom.jpg",
  "logo": "https://allstarreno.com/images/logo.png",
  "sameAs": [
    "https://www.facebook.com/allstarreno",
    "https://www.google.com/maps/place/All-Star+Renovations"
  ],
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "All-Star Renovation Services",
    "itemListElement": [
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "All-Star Shower System Installation"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Walk-In Tub Installation"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Kitchen Remodeling"}}
    ]
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "5.0",
    "reviewCount": "87"
  }
}
```

---

## 2. Service Schema (Service & Sub-Service Pages)

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "serviceType": "Bathroom Remodeling",
  "provider": {
    "@type": "HomeAndConstructionBusiness",
    "name": "All-Star Renovations",
    "url": "https://allstarreno.com"
  },
  "areaServed": {
    "@type": "GeoCircle",
    "geoMidpoint": {
      "@type": "GeoCoordinates",
      "latitude": "35.0887",
      "longitude": "-92.4421"
    },
    "geoRadius": "50000"
  },
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "All-Star Shower Systems",
    "itemListElement": [
      {
        "@type": "Offer",
        "itemOffered": {
          "@type": "Product",
          "name": "All-Star Designer Shower System",
          "description": "Premium solid composite stone shower system with lifetime warranty. 1-2 day installation."
        }
      }
    ]
  },
  "description": "Professional bathroom remodeling including walk-in showers, tub-to-shower conversions, and Aging Safely Walk-In Tubs in Conway and Central Arkansas. Grout-free systems installed in 1-2 days with lifetime material warranties."
}
```

---

## 3. FAQPage Schema (Add to every service + location page)

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "How long does a typical All-Star Shower System installation take in Conway AR?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Most All-Star Shower System transformations are completed in as little as 1-2 days with minimal disruption to your home."
      }
    },
    {
      "@type": "Question",
      "name": "What is the difference between the All-Star Shower System tiers?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "We offer three coordinated tiers: Premier (reliable performance), Signature (elevated design), and Designer Premium (full solid composite stone luxury with the highest durability and beauty)."
      }
    }
  ]
}
```

---

## 4. Location Page Schema (LocalBusiness variant)

Use the main LocalBusiness schema above + add this on each city page:

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "All-Star Renovations - Conway Location",
  "description": "All-Star Renovations provides expert bathroom remodeling, All-Star Shower Systems, and Aging Safely Walk-In Tubs to homeowners in Conway, AR and surrounding Central Arkansas communities.",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Conway",
    "addressRegion": "AR"
  },
  "areaServed": "Conway, AR"
}
```

---

## 5. HowTo Schema Example (Process Pages)

```json
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "How to Get a New All-Star Shower System Installed",
  "step": [
    {
      "@type": "HowToStep",
      "position": 1,
      "name": "Free In-Home Consultation",
      "text": "We visit your home, measure your space, and discuss your goals and budget."
    },
    {
      "@type": "HowToStep",
      "position": 2,
      "name": "Custom Design & Quote",
      "text": "We recommend the perfect All-Star tier and provide a transparent price."
    }
  ]
}
```

---

**Usage Recommendation**:
- Homepage: LocalBusiness + FAQPage
- Service pages: Service + FAQPage + HowTo
- Location pages: LocalBusiness (city-specific) + FAQPage
- Blog posts: Article + FAQPage (when applicable)

I can generate the full combined script for any specific page on request.