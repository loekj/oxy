# OxyClinic longevity landing page

The ad landing page for the Longevity Check. Portuguese (pt-PT) and English, one static `index.html`.

- Live (GitHub Pages): https://loekj.github.io/oxy/
- Planned address: `longevity.oxyclinic.pt`
- Hidden from search engines (`noindex`). Only ad clicks should land here.
- Status: draft. Prices, copy and doctors are still to be confirmed. The booking box is a demo until Zappy is connected.

## Language

The page picks Portuguese or English from the browser. Force it with `?lang=pt-PT` or `?lang=en`.

## Links for ads

The core offer is the Check plus the membership. Ads for single treatments land in the same page, with the treatment already picked in the booking box.

| Ad for | Link |
|---|---|
| Longevity Check (core) | `/?lang=pt-PT#marcar` |
| Treatments, "fits your routine" | `/?lang=pt-PT#rotina` |
| Hyperbaric chamber | `/?t=hbot#marcar` |
| Infrared | `/?t=infrared#marcar` |
| Technogym strength session | `/?t=strength#marcar` |
| Weber laser | `/?t=laser#marcar` |
| Vitamin IV drip | `/?t=iv#marcar` |
| Whole-body hyperthermia | `/?t=hyper#marcar` |

Add `&lang=en` for English ads. Treatment prices in `index.html` (`TREATS`) are examples until confirmed.

## Connect the subdomain

1. At the DNS of `oxyclinic.pt`, add a `CNAME` record: `longevity` → `loekj.github.io`.
2. Add a file `CNAME` to this repo with one line: `longevity.oxyclinic.pt`.
3. In the repo settings, under Pages, turn on "Enforce HTTPS" once the certificate is ready.

Do step 2 only after step 1. Otherwise the GitHub address redirects to a domain that does not answer yet.

## Connect booking (Zappy)

Replace the `#booking-demo` block in `index.html` with the Zappy booking button or embedded form for "Check de Longevidade". Send Zappy's success redirect to a thank-you page that fires the conversion. Load the ad tags in `loadTags()`, which runs only after cookie consent. Never send health details to ad platforms.
