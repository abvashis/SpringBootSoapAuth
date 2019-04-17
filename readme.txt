
https://memorynotfound.com/spring-ws-username-password-authentication-wss4j/

https://vianneyfaiv.re/2017/04/24/spring-ws-how-to-configure-ws-security-auth-for-a-soap-1-1-client/


wsdl : http://localhost:8080/countries/ws/countries.wsdl

Request :

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
				  xmlns:gs="http://spring.io/guides/gs-producing-web-service">
	<soapenv:Header>
		<wsse:Security
			xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"
			mustUnderstand="1">
			<wsse:UsernameToken>
				<wsse:Username>user</wsse:Username>
				<wsse:Password>password</wsse:Password>
			</wsse:UsernameToken>
		</wsse:Security>
	</soapenv:Header>
	<soapenv:Body>
		<gs:getCountryRequest>
         <gs:name>Spain</gs:name>
      </gs:getCountryRequest>
	 </soapenv:Body>
</soapenv:Envelope>


URL:
http://localhost:8080/countries/ws

POST

Response:
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
    <SOAP-ENV:Header/>
    <SOAP-ENV:Body>
        <ns2:getCountryResponse xmlns:ns2="http://spring.io/guides/gs-producing-web-service">
            <ns2:country>
                <ns2:name>Spain</ns2:name>
                <ns2:population>46704314</ns2:population>
                <ns2:capital>Madrid</ns2:capital>
                <ns2:currency>EUR</ns2:currency>
            </ns2:country>
        </ns2:getCountryResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>