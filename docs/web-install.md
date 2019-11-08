---
id: web-install
title: Install the EDC for Frontend Frameworks
sidebar_label: API Installation
---

## Overview

The EDC can be installed independently as an API on a server to allow Frontend Frameworks to make AJAX based calls to retrieve data. This allows all frameworks to receive the benefits of the EDC outlined in the **[overview](overview.md)** when retrieving data.

## Installation

To install the EDC as an API, there are a few prerequisits that have to be met:
1. The EDC requires a pre-existing database to be created. The connection string is necessary during the EDC installation.
2. The application **must** be running .Net Framework (v4.6.1 or above) or .Net Core (v2.2.7).