---
id: embedded-install
title: Add the EDC into a .Net (Framework / Core) Application
sidebar_label: EDC for .Net Applications
---

## Overview

The EDC can be installed into any .Net Framework or .Net Core application as a dll available on [NuGet](https://www.nuget.org/). This allows the application to receive the benefits of the EDC outlined in the **[overview](overview.md)** when retrieving data. Unlike the Web Application API version of the EDC, the dll allows for simplified data retrieval directly from your controller methods without the need for generating Models.

## Installation

To install the EDC dll, there are a few prerequisits that have to be met:
1. The EDC requires a pre-existing SQL Server database to be created. The connection string is necessary during the EDC installation.
2. The application **must** be running the latest version of the .Net Framework (v4.7.2) or .Net Core (v2.2.7).

After the prerequisits have been met:
1. Contact the EDC sales team for a license.
2. In Visual Studio, open the NuGet Package Manager and install EDC.
3. In your project, generate a Startup.cs file that resembles the following:

```
using EDC.Extensions;
using Microsoft.Owin;
using Owin;
using System.Configuration;

[assembly: OwinStartup(typeof(Application.Startup))]

namespace Application
{
    public class Startup
    {
        //Recommended
        private const string IvSalt = "***Generate Custom Salt***";
        private const string SecretKey = "***Generate Custom Secret***";

        //Required
        private const int CacheTimeoutMinutes = 240;
        public void Configuration(IAppBuilder app)
        {

            app.LoadLicense(@"***Provided License Information Here***");

            //Set EDC connection string
            ConfigureDb.UseSqlServer(ConfigurationManager.ConnectionStrings["AppDb"].ConnectionString, IvSalt, SecretKey, CacheTimeoutMinutes);

            //Set up Dashboard and migrate
            app.UseEDCDashboard(typeof(Startup).Assembly);
        }
    }
}
```
When creating the Startup.cs file, it is recommended to provide the system with a Salt and SecretKey in order to encrypt the connection string.

On startup, the system runs app.UseEDCDashboard which scans the environment to make sure that the EDC database has been created and all necessary dependencies are installed. 

4. Start the application and redirect to "/edc" in the browser. If installation was successful, the EDC dashboard will appear and connectors, roles and users can be created.
