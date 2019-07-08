# ![LOGO](logo.png) BikeWise API v2 **flow**ground Connector

## Description

A generated **flow**ground connector for the BikeWise API v2 API (version v2).

Generated from: https://api.apis.guru/v2/specs/bikewise.org/v2/swagger.json<br/>
Generated at: 2019-07-08T14:13:31+03:00

## API Description

<p>This is an API for accessing information about bicycling related incidents. You can find the source code on <a href="https://github.com/bikeindex/bikewise">GitHub</a>.</p>

## Authorization

This API does not require authorization.

## Actions

### Paginated incidents matching parameters
<blockquote><p>If you'd like more detailed information about bike incidents, use this endpoint. For mapping, <code>locations</code> is probably a better bet.</p>

<p><strong>Notes on location searching</strong>: <br />
- <code>proximity</code> accepts an ip address, an address, zipcode, city, or latitude,longitude - i.e. <code>70.210.133.87</code>, <code>210 NW 11th Ave, Portland, OR</code>, <code>60647</code>, <code>Chicago, IL</code>, and <code>45.521728,-122.67326</code> are all acceptable<br />
- <code>proximity_square</code> sets the length of the sides of the square to find matches inside of. The square is centered on the location specified by <code>proximity</code>. It defaults to 100.</p></blockquote>

*Tags:* `incidents`

#### Input Parameters
* `page` - _optional_ - <p>Page of results to fetch.</p>
* `per_page` - _optional_ - <p>Number of results to return per page.</p>
* `occurred_before` - _optional_ - <p>End of period</p>
* `occurred_after` - _optional_ - <p>Start of period</p>
* `incident_type` - _optional_ - <p>Only incidents of specific type</p>
    Possible values: crash, hazard, theft, unconfirmed, infrastructure_issue, chop_shop.
* `proximity` - _optional_ - <p>Center of location for proximity search</p>
* `proximity_square` - _optional_ - <p>Size of the proximity search</p>
* `query` - _optional_ - <p>Full text search of incidents</p>

### GET--version-incidents--id---format-

*Tags:* `incidents`

#### Input Parameters
* `id` - _required_ - <p>Incident ID</p>

### Unpaginated geojson response
<blockquote><p><strong>This endpoint behaves exactly like</strong> <code>incidents</code>, but returns a valid geojson <code>FeatureCollection</code> that looks like this:</p>

<pre><code>{
  type: "FeatureCollection",
  features: [
    {
      type: "Feature",
      properties: {
      id: 4474199,
      type: "Theft",
      occurred_at: 1428536937
    },
      geometry: {
      type: "Point",
      coordinates: [ -122.6244177, 45.5164386 ]
    }
  }
}
</code></pre>

<p>It doesn't paginate. If you pass the <code>all</code> parameter it returns all matches (which can be big, &gt; 4mb), otherwise it returns the 100 most recent.</p>

<p><strong>Go forth and make maps!</strong></p></blockquote>

*Tags:* `locations`

#### Input Parameters
* `occurred_before` - _optional_ - <p>End of period</p>
* `occurred_after` - _optional_ - <p>Start of period</p>
* `incident_type` - _optional_ - <p>Only incidents of specific type</p>
    Possible values: crash, hazard, theft, unconfirmed, infrastructure_issue, chop_shop.
* `proximity` - _optional_ - <p>Center of location for proximity search</p>
* `proximity_square` - _optional_ - <p>Size of the proximity search</p>
* `query` - _optional_ - <p>Full text search of incidents</p>
* `limit` - _optional_ - <p>Max number of results to return. Defaults to 100</p>
* `all` - _optional_ - <p>Give 'em all to me. Will ignore limit</p>

### Unpaginated geojson response with simplestyled markers
<blockquote><p>This behaves exactly like the root <code>locations</code> endpoint, but returns <a href="https://github.com/mapbox/simplestyle-spec">simplestyled markers</a> (<a href="https://www.mapbox.com/guides/markers/#simple-style">mapbox styled markers</a>)</p>

<p><strong>Go forth and make maps!</strong></p></blockquote>

*Tags:* `locations`

#### Input Parameters
* `occurred_before` - _optional_ - <p>End of period</p>
* `occurred_after` - _optional_ - <p>Start of period</p>
* `incident_type` - _optional_ - <p>Only incidents of specific type</p>
    Possible values: crash, hazard, theft, unconfirmed, infrastructure_issue, chop_shop.
* `proximity` - _optional_ - <p>Center of location for proximity search</p>
* `proximity_square` - _optional_ - <p>Size of the proximity search</p>
* `query` - _optional_ - <p>Full text search of incidents</p>
* `limit` - _optional_ - <p>Max number of results to return. Defaults to 100</p>
* `all` - _optional_ - <p>Give 'em all to me. Will ignore limit</p>

## License

**flow**ground :- Telekom iPaaS / bikewise-org-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
