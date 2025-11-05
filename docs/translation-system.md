---
title: Translation System
nav_order: 6
---

# Translation System

The **Warehouse module** supports multilingual text rendering to provide a consistent user experience across both **English (EN)** and **Arabic (AR)** interfaces.  
It integrates directly with the ERP’s centralized **Translations module**, ensuring all text labels and messages remain synchronized.

---

## ⚙️ How It Works

- Text is rendered using standard **Blade/PHP localization helpers**:
  ```php
  {{ trans('...') }}
  {{ __('...') }}
  @lang('...')
