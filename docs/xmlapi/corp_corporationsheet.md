## CorporationSheet

* __Path:__ ``/corp/CorporationSheet.xml.aspx``
* __Access mask:__ 8
* __Cache timer:__ 5 hours 57 minutes
* __Parameters:__
    <table>
        <tbody>
            <tr>
                <th>Argument</th>
                <th>Type</th>
                <th>Meaning</th>
            </tr>
            <tr>
                <td>keyID</td>
                <td><strong>long</strong></td>
                <td>API key ID</td>
            </tr>
            <tr>
                <td>vCode</td>
                <td><strong>char</strong></td>
                <td>API verification code</td>
            </tr>
            <tr>
                <td>corporationID</td>
                <td><strong>long</strong></td>
                <td>ID of corporation</td>
            </tr>
        </tbody>
    </table>

    or for <a href="#no-key">limited access</a>

    <table>
        <tbody>
            <tr>
                <th>Argument</th>
                <th>Type</th>
                <th>Meaning</th>
            </tr>
            <tr>
                <td>corporationID</td>
                <td><strong>long</strong></td>
                <td>ID of corporation</td>
            </tr>
        </tbody>
    </table>

### Sample Response

```xml
<?xml version='1.0' encoding='UTF-8'?>
<eveapi version="2">
    <currentTime>2010-02-26 05:34:14</currentTime>
    <result>
        <corporationID>150212025</corporationID>
        <corporationName>Banana Republic</corporationName>
        <ticker>BR</ticker>
        <ceoID>150208955</ceoID>
        <ceoName>Mark Roled</ceoName>
        <stationID>60003469</stationID>
        <stationName>Jita IV - Caldari Business Tribunal Information Center</stationName>
        <description>Garth's testing corp of awesome sauce, win sauce as it were. In this
                     corp...&lt;br&gt;&lt;br&gt;IT HAPPENS ALL OVER</description>
        <url>some url</url>
        <allianceID>150430947</allianceID>
        <allianceName>The Dead Rabbits</allianceName>
        <taxRate>93.7</taxRate>
        <memberCount>3</memberCount>
        <memberLimit>6300</memberLimit>
        <shares>1</shares>
        <rowset name="divisions" key="accountKey" columns="accountKey,description">
            <row accountKey="1000" description="Division 1"/>
            <row accountKey="1001" description="Division 2"/>
            <row accountKey="1002" description="Division 3"/>
            <row accountKey="1003" description="Division 4"/>
            <row accountKey="1004" description="Division 5"/>
            <row accountKey="1005" description="Division 6"/>
            <row accountKey="1006" description="Division 7"/>
        </rowset>

        <rowset name="walletDivisions" key="accountKey" columns="accountKey,description">
            <row accountKey="1000" description="Wallet Division 1"/>
            <row accountKey="1001" description="Wallet Division 2"/>
            <row accountKey="1002" description="Wallet Division 3"/>
            <row accountKey="1003" description="Wallet Division 4"/>
            <row accountKey="1004" description="Wallet Division 5"/>
            <row accountKey="1005" description="Wallet Division 6"/>
            <row accountKey="1006" description="Wallet Division 7"/>
        </rowset>
        <logo>
            <graphicID>0</graphicID>
            <shape1>448</shape1>
            <shape2>0</shape2>
            <shape3>418</shape3>
            <color1>681</color1>
            <color2>676</color2>
            <color3>0</color3>
        </logo>
    </result>
    <cachedUntil>2010-02-26 11:34:14</cachedUntil>
</eveapi>
```

### No key
Public details of any corporation can be retrieved without an API key.

__Parameters:__
    <table>
        <tbody>
            <tr>
                <th>Argument</th>
                <th>Type</th>
                <th>Meaning</th>
            </tr>
            <tr>
                <td>corporationID</td>
                <td><strong>long</strong></td>
                <td>ID of corporation</td>
            </tr>
        </tbody>
    </table>

Notes.
If you pass both corporationID and the other parameters to the API server it will return the non-member version of the information just like you had only passed it corporationID.

### Sample response

```xml
<?xml version='1.0' encoding='UTF-8'?>
<eveapi version="1">
    <currentTime>2007-12-02 19:41:53</currentTime>
    <result>
        <corporationID>150333466</corporationID>
        <corporationName>Marcus Corp</corporationName>
        <ticker>MATT2</ticker>
        <ceoID>150302299</ceoID>
        <ceoName>Marcus</ceoName>
        <stationID>60003469</stationID>
        <stationName>Jita IV - Caldari Business Tribunal Information Center</stationName>
        <description>Another Corp</description>
        <url />
        <allianceID>150382481</allianceID>
        <allianceName>Starbase Anchoring Alliance</allianceName>
        <taxRate>0</taxRate>
        <memberCount>1</memberCount>
        <shares>1000</shares>
        <logo>
            <graphicID>0</graphicID>
            <shape1>488</shape1>
            <shape2>0</shape2>
            <shape3>0</shape3>
            <color1>0</color1>
            <color2>0</color2>
            <color3>0</color3>
        </logo>
    </result>
    <cachedUntil>2007-12-03 01:41:53</cachedUntil>
</eveapi>
```

### Result Data

* __Corporation Sheet:__
    <table>
        <tbody>
            <tr>
                <td>Name</td>
                <td>Data Type</td>
                <td>Description</td>
            </tr>
            <tr>
                <td>corporationID</td>
                <td>long</td>
                <td>Corporation ID</td>
            </tr>
            <tr>
                <td>corporationName</td>
                <td>string</td>
                <td>Name of the Corporation.</td>
            </tr>
            <tr>
                <td>ticker</td>
                <td>string</td>
                <td>Corp Ticker, often used as a nickname.</td>
            </tr>
            <tr>
                <td>ceoID</td>
                <td>long</td>
                <td>Character ID of the CEO. This will be 1 for closed corps.</td>
            </tr>
            <tr>
                <td>ceoName</td>
                <td>string</td>
                <td>Character Name of the CEO. This will be 'EVE System' for closed corps.</td>
            </tr>
            <tr>
                <td>stationID</td>
                <td>long</td>
                <td>Station ID of the Corporation HQ.</td>
            </tr>
            <tr>
                <td>stationName</td>
                <td>string</td>
                <td>Station Name of the Corporation HQ.</td>
            </tr>
            <tr>
                <td>description</td>
                <td>string</td>
                <td>Corp Description Text</td>
            </tr>
            <tr>
                <td>url</td>
                <td>string</td>
                <td>Corporation URL.</td>
            </tr>
            <tr>
                <td>allianceID</td>
                <td>long</td>
                <td>Alliance ID, if any.</td>
            </tr>
            <tr>
                <td>allianceName</td>
                <td>string</td>
                <td>Alliance Name, if any. Is null if not present.</td>
            </tr>
            <tr>
                <td>taxRate</td>
                <td>double</td>
                <td>Taxes on missions and ratting.</td>
            </tr>
            <tr>
                <td>memberCount</td>
                <td>int</td>
                <td>Current number of Members.</td>
            </tr>
            <tr>
                <td>memberLimit</td>
                <td>int</td>
                <td>Maximum number of members based on CEO corp Management skills.</td>
            </tr>
            <tr>
                <td>shares</td>
                <td>int</td>
                <td>Shares outstanding.</td>
            </tr>
        </tbody>
    </table>

* __Corporation Divisions rowset:__
    <table>
        <tr>
            <td>Name</td>
            <td>Data Type</td>
            <td>Description</td>
         </tr>
         <tr>
             <td>accountKey</td>
             <td>int</td>
             <td>Division key.</td>
         </tr>
         <tr>
             <td>description</td>
             <td>string</td>
             <td>Division (corp hangar) Label.</td>
         </tr>
    </table>

* __Corporation Wallet Divisions rowset:__
    <table>
        <tr>
            <td>Name</td>
            <td>Data Type</td>
            <td>Description</td>
         </tr>
         <tr>
             <td>accountKey</td>
             <td>int</td>
             <td>Wallet ID.</td>
         </tr>
         <tr>
             <td>description</td>
             <td>string</td>
             <td>Wallet label.</td>
         </tr>
    </table>

* __Corporation Logo:__
    <table>
        <tr>
            <td>Name</td>
            <td>Data Type</td>
            <td>Description</td>
         </tr>
         <tr>
             <td>graphicID</td>
             <td>int</td>
             <td>Corporation ID of the member corporation.</td>
         </tr>
         <tr>
             <td>shape1</td>
             <td>int</td>
             <td>Shape ID #</td>
         </tr>
         <tr>
             <td>shape2</td>
             <td>int</td>
             <td>Shape ID #</td>
         </tr>
         <tr>
             <td>shape3</td>
             <td>int</td>
             <td>Shape ID #</td>
         </tr>
         <tr>
             <td>color1</td>
             <td>int</td>
             <td>Color ID #</td>
         </tr>
         <tr>
             <td>color2</td>
             <td>int</td>
             <td>Color ID #</td>
         </tr>
         <tr>
             <td>color3</td>
             <td>int</td>
             <td>Color ID #</td>
         </tr>
    </table>
