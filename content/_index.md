+++
title = "Your Radio Station Name"
description = "Welcome to the best radio broadcasts, episodes, and live shows."
template = "index.html"  # Assumes your theme has an index.html template; adjust if needed
sort_by = "date"
paginate_by = 5  # Optional: Paginate recent episodes or posts
+++

Welcome to the station! Check out our latest episodes below.

{{ section.content | safe }}
