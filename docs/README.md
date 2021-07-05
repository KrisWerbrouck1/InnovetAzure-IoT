# IoT Central

## Doelstelling

* Visualiseren op een dashboard van data afkomstig van een IoT-device (microcontroller of Raspberry Pi).
* Actuatoren op een IoT-device aansturen met een dashboard.

Er wordt gebruik gemaakt van Azure IoT-Central van Microsoft.


![figuur](./assets/08f05638e9d367934c610eb63ad1608d.png)

## Inleiding

Azure is de cloud computing omgeving van Microsoft. Bij de cloud denken we
meestal aan het online bewaren van data (foto’s, documenten, .. ) bij One Drive,
Dropbox, Google Drive of een andere cloud opslag dienst.

Bij de cloud staat de data echter altijd op een fysieke server. Deze fysieke
server staat echter niet bij je thuis maar in een datacenter.

Enkele voorbeelden van datacenters bij Microsoft:

<https://www.youtube.com/watch?v=80aK2_iwMOs>

<https://www.youtube.com/watch?v=9nLD7bc5O1g>

Bij cloud computing is het ook mogelijk om zelf virtuele servers op te zetten.
Hierbij maak je een virtuele server aan op een fysische server in het
datacenter. Deze virtuele server kan vervolgens dienst doen als webserver,
database, analyseren van data, ..

Enkele voordelen van cloud computing zijn:

-   Er moet door de gebruiker geen eigen hardware en software aangekocht worden
    voor een eigen datacenter.

-   De beveiliging van de infrastructuur zit bij de cloud provider.

-   De cloud provider maakt back-ups van de gegevens waardoor deze niet verloren
    kunnen gaan.

-   De rekenkracht van het datacenter wordt verdeeld over alle gebruikers van
    het datacenter.

De gebruiker moet enkel over een computer met internettoegang en een browser
beschikken. Via een portal krijgt de gebruiker toegang tot de nodige servers.

Meer uitleg over cloud computing kan je nalezen op
[https://www.true.nl/blog/wat-is-azure/] (<https://www.true.nl/blog/wat-is-azure/>)

## De portal van de azure cloud omgeving

![figuur](./assets/494f5fcf240aa25b26d446e022ca77ce.png)

Er zijn een aantal modellen mogelijk. Zowel SaaS (Software as a Service), Paas
(Platform as a Service) en IaaS (Infrastructure as a Service) zijn mogelijk met
Azure.

![figuur](./assets/bef1673d6514288c44d8c850866a80d3.png)

![figuur](./assets/49215cd1654e32ec2a6703d8a6cdb690.png)

### On-Premises 
Dit is geen cloudmodel. Alle servers, software, data en applicaties staan bij de gebruiker.


### IaaS        
Dit cloudservicemodel komt het dichtst in de buurt van het beheren van fysieke servers. Een cloudprovider houdt de hardware up-to-date, maar het onderhoud van het besturingssysteem en de netwerkconfiguratie blijft een taak van de gebruiker. Een voordeel van dit cloudservicemodel is de snelle implementatie van nieuwe toestellen. Het instellen van een nieuwe virtuele machine gaat aanzienlijk sneller dan het aanschaffen, installeren en configureren van een fysieke server. 

### PaaS        
Dit cloudservicemodel is een beheerde hostingomgeving. De cloudprovider beheert de virtuele machines en netwerkresources en de gebruiker implementeert de bijbehorende toepassingen in de beheerde hostingomgeving. 

### SaaS
In dit cloudservicemodel beheert de cloudprovider alle aspecten van de toepassingsomgeving, zoals virtuele machines, netwerkresources, gegevensopslag en toepassingen. De gebruiker hoeft alleen maar de gegevens op te geven bij de toepassing die door de cloudprovider wordt beheerd. 

##  Registratie Azure

Een gratis studentenaccount kan aangemaakt worden op
[<https://azure.microsoft.com/nl-nl/free/students/>](<https://azure.microsoft.com/nl-nl/free/students/>)

Registreer je met je e-mailadres van school. Wanneer je registreert met een
ander e-mailadres, krijg je de vraag om met het e-mailadres van de school te
registeren.

![figuur](./assets/62d297c9ab6687d4b80a1cc365aba6e2.png)

Vul je telefoonnummer in als verificatie.

![figuur](./assets/2732bef4b83dadd26be838012d396e03.png)

Registreer je.

![figuur](./assets/74ab47a78c5de8598fba159945c342e5.png)

Ga akkoord met de voorwaarden.

![figuur](./assets/25ef2cc500229433cedf669b34edda08.png)

## Resourcegroep

Wanneer je iets wil maken in Azure (Virtuele server, IoT-Hub, IoT-Central,
database, …) moet er een resourcegroep aangemaakt worden.

Kies "+ Een resource maken".

![figuur](./assets/cb91768b6e0b4b6cc18e4d624a823e99.png)

Geef in het zoekvenster "Resourcegroep" in.

![figuur](./assets/b52c17b676b69883eb728421a18bc46f.png)

Klik op Maken.

![figuur](./assets/fbfe568b86a3355d54e094b270a98848.png)

Geef de resourcegroep een zelfgekozen naam en kies de dichtste locatie om de
resourcegroep te bewaren.

![figuur](./assets/ce8a9ffb4e6c4d51587da3705d09f7b3.png)

Klik vervolgens op "Beoordelen en maken".

![figuur](./assets/2def2ce6162b4121b9379a904c0aaf53.png)

## Azure IoT-Central

Azure IoT-Central maakt gebruik van het SaaS (Software as a Service) model. In
deze cursus stuurt een IoT-apparaat (ESP8266, ESP32 of raspberry pi) data door
naar Azure IoT-Cental. De data (random temperatuur en luchtvochtigheid) wordt vervolgens weergegeven op een dashboard in je browser.

Eveneens wordt een actuator op het IoT-apparaat (led) bediend vanuit het dashboard.

Na het realiseren van dit voorbeeld ben je in staat om in combinatie met de andere cursussen op [https://stem-ict.be/](<https://stem-ict.be/>) data afkomstig van een sensor door te sturen naar
IoT-Central en actuatoren aan te sturen.

![figuur](./assets/9bfd053cc105f0726f41db12e536affa.png)

Met het gratis pakket kunnen 30 000 berichten per maand verzonden worden.

![figuur](./assets/84f9a833c2fba26ba5f04b5be0843341.png)

## Aanmaak IoT-Central

Azure IOT-Central is een cloud applicatie (SaaS).

Maak deze cloud applicatie aan door in de portal te klikken op “+ Een resource
maken”.

![figuur](./assets/cb91768b6e0b4b6cc18e4d624a823e99.png)

Geef in het zoekvenster “IoT Central application” in:

![figuur](./assets/e5f1aadfd57d3d72d70ee33dd21c2308.png)

Klik op "Maken".

![figuur](./assets/ab75efa84350579f76ebd08fe39b20c0.png)

Vul een zelfgekozen Resourcenaam in. De URL van je aangemaakte IoT-Central applicatie is gebaseerd op je zelfgekozen
Resourcenaam. Selecteer het studentenabonnement en de vooraf aangemaakte
Resourcegroep.

Kies voor aangepaste toepassing als sjabloon en de dichtste locatie.

![figuur](./assets/cbc36ea270a2b056bdb1d1b4dff32202.png)

Wanneer alles goed gelukt is krijg je de melding dat de implementatie goed
gelukt is.

![figuur](./assets/a434d2b2b4a8e688809a27e014c0b1e2.png)

Selecteer in de Azure portal de zelf aangemaakte IoT-Central-toepassing.

![figuur](./assets/66b884628551edd9a134b979ca7350ec.png)

Klik op de URL van de aangemaakte toepassing.

![figuur](./assets/4e1944b80ccaa191abdad00b0befc266.png)

Je komt op de portal van de aangemaakte IoT Central toepassing.

![figuur](./assets/c9766b2ec1a2497e45ba38f457cbd36f.png)

## Aanmaken Apparaatsjabloon

Voor een nieuw IoT-device moet eerst een sjabloon apparaat aangemaakt worden.

Maak een Apparaatsjabloon aan door op "Apparaatsjablonen" te klikken in de linker
balk. Kies vervolgens “+Nieuw”.

![figuur](./assets/8a80e6d102e0a5510db3cf642a032205.png)

Kies als type “IoT-apparaat” en klik op “Volgende: Aanpassen”.

![figuur](./assets/03df1ede7f61a411e84435e6cc67da75.png)

Voer een zelfgekozen naam in voor het apparaatsjabloon en klik op Volgende:
Beoordelen.

![figuur](./assets/a13e809337d04c9e318877f3df8b8125.png)

Klik op “Maken”.

![figuur](./assets/5cfe05e919214aae6820a440cce20f0d.png)

Wanneer het sjabloon aangemaakt is krijg je bevestiging.

![figuur](./assets/d20a0bd3b1e445110206af545fa3bdaf.png)

## Interface toevoegen

We voorzien voor het apparaat een interface. Een interface wordt gebruikt om een
sensorwaarde in te lezen of een actuator aan te sturen. In het voorbeeld
voorzien we het inlezen van 2 sensorenwaardes en aansturen van 1 actuator.

Klik op Aangepast model.

![figuur](./assets/aa50a94dbc806e4823e551106aa9a6ed.png)

Klik op “Mogelijkheid toevoegen aan standaardonderdeel” en vul de gekozen
weergavenaam in. Wanneer je sensordata wil inlezen staat “Type van …” op
Telemetry. Het is eveneens mogelijk een eenheid toe te voegen. Dit is echter
geen verplichting.

![figuur](./assets/36e61f89bef7a980dbe11677908227fe.png)

Klik op “+ Een mogelijkheid toevoegen” om de 2de waarde van de interface toe te
voegen.

![figuur](./assets/eeda3ca3103e3e12e53827f9be4a4f81.png)

Indien we een actuator toevoegen moet je “Telemetry” aanpassen naar “Command”. In het voorbeeld schakelen we een led in en uit. Voorzie hiervoor 2 commando's.

![figuur](./assets/InterfaceToevoegen.png)

Klik op “Opslaan” om de interface te bewaren.

## Visuele weergave

Kies onder “Weergave” op “Het apparaat visualiseren”.

![figuur](./assets/1d5a1daa3267a67f3e49e019d9fe7211.png)

Om sensordata grafisch weer te geven kies je de waarde onder Telemetrie. Klik vervolgens op “Tegel
toevoegen”.

![figuur](./assets/120b5dc777ec7ba70dfb15719c165829.png)

Om een actuator vanop het dashboard te bedienen kies je het commando onder Opdrachten. Klik vervolgens op “Tegel
toevoegen”.

![figuur](./assets/ActuatorGrafischWeergeven.png)

Wanneer alles waardes toegevoegd zijn klik je op “Opslaan”.

![figuur](./assets/f310f36306024fa8d8cb98f81e18aae0.png)

Voor het sjabloon bruikbaar is moet dit gepubliceerd worden. Klik hiervoor op
“Publiceren”.

![figuur](./assets/25af427adcc885a0fdea5bc481d029cc.png)

Klik nogmaals op “Publiceren”.

![figuur](./assets/9ae022fd294fe5372c4a1edde08c200a.png)

## Aanmaken apparaat

Maak vanuit het sjabloon een nieuw apparaat aan. Klik op “+ Nieuw” in Alle
apparaten.

![figuur](./assets/29277cf41fd2e55d35c1a39851bc3a75.png)

Selecteer het ontworpen Apparaatsjabloon, pas indien nodig de apparaatnaam aan.

![figuur](./assets/17ddfd2f71c7c15b2ef22d9515b004bc.png)

## ESP8266 arduino

In het voorbeeld sturen we data door met een ESP8266 microcontroller (thing)
naar Azure IOT-Central.

![figuur](./assets/IoThubESP8266.png)

De voorbeeldcode is gebaseerd op <https://github.com/Azure/iot-central-firmware>
Download eventueel de volledige repository en unzip
deze.![figuur](./assets/a91f4249a1bf3b1ccd47dc2fcbb2d639.png)

De voorbeeldcode voor de esp8266 is te vinden onder het pad ESP8266. Het arduino
bestand is esp8266.ino. De nodige bestanden in de scr map moeten zeker altijd
aanwezig zijn bij het arduino bestand.

Vul de gegevens van het wifi netwerk in:

```cpp
#define WIFI_SSID "<ENTER WIFI SSID HERE>"
#define WIFI_PASSWORD "<ENTER WIFI PASSWORD HERE>"
```

De volgende delen code zijn afhankelijk van de instellingen in Azure IOT-central

```cpp
const char* SCOPE_ID = "<ENTER SCOPE ID HERE>";
const char* DEVICE_ID = "<ENTER DEVICE ID HERE>";
const char* DEVICE_KEY = "<ENTER DEVICE primary/secondary KEY HERE>";
```

De gegevens van het apparaat zijn te vinden in IoT-Central onder « Verbinding
met »:

![figuur](./assets/a959263696de15863df868ee3a3b996d.png)

Vul het « id-bereik », de « Apparaat-id » en de « primaire sleutel » in de
arduino code in.

![figuur](./assets/abbd1b0a8031e536c1ba65db33a22d13.png)

Een voorbeeldprogramma met 2 tellers. Indien je andere waardes wil doorsturen in
een praktische toepassing pas je volgende stukje code aan:

```cpp
pos = snprintf(msg, sizeof(msg) - 1, "{\"teller1\": %d, \"teller2\":%d}", teller1, teller2);
```

De totale code:

```cpp
// Copyright (c) Microsoft. All rights reserved.
// Licensed under the MIT license. See LICENSE file in the project root for full
// license information.

// This gist is based on https://github.com/Azure/iot-central-firmware/blob/master/ESP8266/ESP8266.ino

#include <ESP8266WiFi.h>
#include "src/iotc/common/string_buffer.h"
#include "src/iotc/iotc.h"

#define WIFI_SSID "SSID"
#define WIFI_PASSWORD "PASW"

const char* SCOPE_ID = "SCOPE_ID";
const char* DEVICE_ID = "DEVICE_ID";
const char* DEVICE_KEY = "DEVICE_KEY";

int teller1=0;
int teller2=0;

void on_event(IOTContext ctx, IOTCallbackInfo* callbackInfo);
#include "src/connection.h"

void on_event(IOTContext ctx, IOTCallbackInfo* callbackInfo) {
  // ConnectionStatus
  if (strcmp(callbackInfo->eventName, "ConnectionStatus") == 0) {
    LOG_VERBOSE("Is connected ? %s (%d)",
                callbackInfo->statusCode == IOTC_CONNECTION_OK ? "YES" : "NO",
                callbackInfo->statusCode);
    isConnected = callbackInfo->statusCode == IOTC_CONNECTION_OK;
    return;
  }

  // payload buffer doesn't have a null ending.
  // add null ending in another buffer before print
  AzureIOT::StringBuffer buffer;
  if (callbackInfo->payloadLength > 0) {
    buffer.initialize(callbackInfo->payload, callbackInfo->payloadLength);
  } 
  LOG_VERBOSE("- [%s] event was received. Payload => %s\n",
              callbackInfo->eventName, buffer.getLength() ? *buffer : "EMPTY");
  
  if (strcmp(callbackInfo->eventName, "Command") == 0) {
    LOG_VERBOSE("- Command name was => %s\r\n", callbackInfo->tag);
  }
  
  if (strcmp(callbackInfo->eventName, "SettingsUpdated") == 0) {
    LOG_VERBOSE("- Setting name was => %s\r\n", callbackInfo->tag);
  }
}

void setup() {
  Serial.begin(9600);

  connect_wifi(WIFI_SSID, WIFI_PASSWORD);
  connect_client(SCOPE_ID, DEVICE_ID, DEVICE_KEY);

  if (context != NULL) {
    lastTick = 0;  // set timer in the past to enable first telemetry a.s.a.p
  }
}

void loop() {
  if (isConnected) {
    unsigned long ms = millis();
    if (ms - lastTick > 5000) {  // send telemetry every 5 seconds
      char msg[128] = {0};
      int pos = 0, errorCode = 0;

      lastTick = ms;
      teller1++;
      teller2=teller2+2;
       
      pos = snprintf(msg, sizeof(msg) - 1, "{\"teller1\": %d, \"teller2\":%d}", teller1, teller2);
      errorCode = iotc_send_telemetry(context, msg, pos);

      msg[pos] = 0;

      if (errorCode != 0) {
        LOG_ERROR("Sending message has failed with error code %d", errorCode);
      }
    }

    iotc_do_work(context);  // do background work for iotc
  } else {
    iotc_free_context(context);
    context = NULL;
    connect_client(SCOPE_ID, DEVICE_ID, DEVICE_KEY);
  }
}
```



## ESP8266 en ESP32 arduino

In het voorbeeld sturen we data door met een ESP8266 of ESP32 microcontroller (thing)
naar Azure IOT-Central. Eveneens sturen we vanop het dashboard in Azure IoT-Central een actuator aan op de ESP8266 of ESP32.

![figuur](./assets/IoThubESP32.png)

Download het voorbeeldprogramma van volgende github pagina. [https://github.com/VTITorhout/IoT_ESP_Azure](<https://github.com/VTITorhout/IoT_ESP_Azure>)

Opteer eventueel om de volledige code als zip file te downloaden.

De instellingen van het wifi netwerk en de verbinding met Azure is mogelijk in de config.h file.

Vul de gegevens van het wifi netwerk in:

```cpp
#define WIFI_SSID "<ENTER WIFI SSID HERE>"
#define WIFI_PSK "<ENTER WIFI PASSWORD HERE>"
```

In het voorbeeld is de ingebouwde led van het Firebeetle ESP32 board de actuator die verbonden is met pin 2. Pas dit indien nodig aan bij een ander bord.

```cpp
#define DBG_PIN	2					            //LED is connected to GPIO2 on the Firebeetle ESP32 board
```

Zorg dat IOT-Central op true staat.

```cpp
#define IOT-Central true
```
Met volgende regel code kan ingesteld worden om de hoeveel tijd info naar Azure verzonden wordt.

```cpp
#define IOT_UPDATE	300				//send new message to cloud every x seconds
```

Via polling wordt gecontrolleerd of de toestand van een acutator moet veranderen. Met volgende regel code wordt ingesteld
om de hoeveel seconden gecontrolleerd wordt.

```cpp
#define POLL_TIME	60				//check for new C2D message every x seconds
```

De volgende delen code zijn afhankelijk van de instellingen in Azure IOT-central

```cpp
const char* SCOPE_ID = "<ENTER SCOPE ID HERE>";
const char* DEVICE_ID = "<ENTER DEVICE ID HERE>";
const char* DEVICE_KEY = "<ENTER DEVICE primary/secondary KEY HERE>";
```

De gegevens van het apparaat zijn te vinden in IoT-Central onder « Verbinding
met »:

![figuur](./assets/a959263696de15863df868ee3a3b996d.png)

Vul het « id-bereik », de « Apparaat-id » en de « primaire sleutel » in de
arduino code in.

![figuur](./assets/abbd1b0a8031e536c1ba65db33a22d13.png)

De totale code van de config file:

```cpp
//Global settings (hardware, WiFi credentials)
	#define WIFI_SSID "<ENTER WIFI SSID HERE>"	    //set to SSID to connect to
	#define WIFI_PSK "<ENTER WIFI PASSWORD HERE>"	//set to password of the SSID

	#define USE_LAN		false			            //set true if wired network must be used
										            //removing this setting will use WiFi
										            //will only work with Wizznet SPI board on ESP8266
										            //other libraries are needed for ESP32 (future?)

	#define ETH_CS	4					            //wired ethernet WIZ5500 CS pin
	
	#define DBG_PIN	2					            //LED is connected to GPIO2 on the Firebeetle ESP32 board

//Azure interface setup
	#define IOT_CENTRAL	true			            //set to true if we use central, if false, direct hub access will be used
	#define SAS_RENEW	15    			            //SAS regenerate every x minutes
	#define IOT_UPDATE	300				            //send new message to cloud every x seconds
	#define POLL_TIME	60				            //check for new C2D message every x seconds

//Azure credentials
	//when using hub, a primary connection string is needed (containing hostname, device and SAS key)
	//	--> you can find this connection string in the azure portal
	const char* primaireVerbindingsreeks = "<primaire verbindingsreeks IoT-Hub>";

	//when using central, you have to provide the scope, device and key
	//	--> you can find these settings in the azure portal
    const char* SCOPE_ID = "<ENTER SCOPE ID HERE>";
    const char* DEVICE_ID = "<ENTER DEVICE ID HERE>";
    const char* DEVICE_KEY = "<ENTER DEVICE primary/secondary KEY HERE>";


```
De data wordt in json formaat doorgezonden. In onderstaande  voorbeeld worden de devicenaam, de tijd en 2 random waarde doorgezonden.

```cpp
 String json = "{\"device\":\""    + (String)prefixedMac +
                "\",\"timestamp\":\"" + time(nullptr) +
                "\",\"rand1\":\"" + random(1, 100000) +
                "\",\"rand2\":\"" + random(1, 100000) +
                "\"}";
  return json;
```
De totale arduino code:

```cpp
#include "config.h"					//contains all settings needed for network & credentials
#include "src/ntp/ntp.h"			//library for timekeeping (needed for httpS)
#include "src/azure/iot.h"			//library to access IoT central/hub on Azure

IoT azure;							//create class azure of type IoT

#if defined(ARDUINO_ARCH_ESP8266)
	#include <ESP8266WiFi.h>		//needed for MAC
#elif defined(ARDUINO_ARCH_ESP32)
	#include <WiFi.h>				//needed for MAC
#endif

#if defined USE_LAN && USE_LAN == true
	#include <SPI.h>
	#include "src/eth/ethernet.h"	//adapted version because @2.0.0 from Arduino give errors and @1.0.4 included in ESP is too old
#endif

//create enum for wired network steps
typedef enum{
	NOT_YET_INITIALIZED,	//no setup has been done
	INITIALIZED_OK,			//found Wizz hardware
	INITIALIZED_NOK,		//did not found Wizz hardware
	CABLE_DISCONNECTED,		//not connected to transport medium
	DHCP					//received IP from DHCP
} NETWORK_STATUS;

/*Next subroutine will create a char array
	--> prefix can be given, e.g. IoT
	--> prefix will be seperated from MAC with a dash
	--> last 6 hex values of MAC of device will be added to the array
*/
void ssidPrefixMac(char* buff, const char* prefix) {
  uint8_t macAddr[6];
  WiFi.softAPmacAddress(macAddr);					//get the MAC
  for (uint8_t i = 0; i < strlen(prefix); i++) {	//add the prefix to the array
    buff[i] = prefix[i];
  }
  buff[strlen(prefix)] = '-';						//add a dash as seperator sign
  for (uint8_t i = 0; i < 3; i++) {					//add the last 3 bytes of the MAC
    sprintf(&buff[strlen(prefix) + 1 + i * 2], "%02X", macAddr[i + 3]);
  }
  buff[strlen(prefix) + 7] = '\0';					//null terminated array
}

/*Next subroutine will setup the network, depending on user needs
	--> WiFi can be used on ESP8266 or ESP32
	--> Wired network can be used on ESP8266 (through Wizznet SPI)
	--> Wired network will not work on ESP32, this is not (yet) implemented
	(different libraries need to be used, because ESP32 does have a MAC)
*/
void setupNetwork() { 
	#if defined USE_LAN && USE_LAN == true	//check if we want WiFi or Wired network connection
		NETWORK_STATUS wiredStatus = NOT_YET_INITIALIZED;
		Serial.println("ETH:\tSetup");
		//SPI.pins(6, 7, 8, 0);				//switch to flash SPI0 (extended mode)
		Ethernet.init(ETH_CS);				//set CS pin --> see config.h
		uint8_t macAddr[6];
		WiFi.softAPmacAddress(macAddr);		//will use MAC of WiFi for Wired
		//Try to get IP from DHCP
		//If failed, check why?
		while (!Ethernet.begin(macAddr, 1000, 1000)) {	//begin DHCP request with timeout of 1 second --> blocking code!
			if (wiredStatus==NOT_YET_INITIALIZED) {
				switch (Ethernet.hardwareStatus()) {
					case 0:	Serial.println("\tNo hardware detected.");
							wiredStatus = INITIALIZED_NOK; //no hardware found
							break;
					case 1:	Serial.println("\tWizNet W5100 detected.");
							wiredStatus = INITIALIZED_OK; //init passed
							break;
					case 2:	Serial.println("\tWizNet W5200 detected.");
							wiredStatus = INITIALIZED_OK; //init passed
							break;
					case 3: Serial.println("\tWizNet W5500 detected.");
							wiredStatus = INITIALIZED_OK; //init passed
							break;
					default:Serial.println("\tUNKNOWN hardware");
							wiredStatus = INITIALIZED_NOK; //no usefull hardware found
				}
			}
			if (wiredStatus == INITIALIZED_OK) {
				//once initialized, check link status
				if (Ethernet.linkStatus() == LinkOFF) {
					//first time here, print the problem
					Serial.write("\tEthernet cable is not connected.\n");
					wiredStatus = CABLE_DISCONNECTED;
				}
			} else {
				while (true) {
					delay(1); // do nothing, no point running with none or unknown hardware
				}
			}
		}
		//passed DHCP init, so IP received
		wiredStatus = DHCP;
		Serial.print("\n\tGot wired IP: ");
		Serial.println(Ethernet.localIP());
	#else
		//use WiFi
		Serial.println("WIFI:\tsetup");
		WiFi.mode(WIFI_STA);
		//create hostname for device, based on prefix and mac
		char prefixedMac[3 + 1 + 6 + 1];	//prefix of 3 characters, 1 dash, 6 hex values of MAC and 1  terminating character
		ssidPrefixMac(&prefixedMac[0], "IoT");
		#if defined(ARDUINO_ARCH_ESP8266)
			WiFi.hostname(prefixedMac);
		#elif defined(ARDUINO_ARCH_ESP32)
			WiFi.config(INADDR_NONE, INADDR_NONE, INADDR_NONE); // Workaround: makes setHostname() work
			WiFi.setHostname(prefixedMac);
		#endif
		Serial.print("\tconnecting ");
		WiFi.begin(WIFI_SSID, WIFI_PSK);	//set credentials in config.h
		while (WiFi.status() != WL_CONNECTED) {
			delay(250);
			Serial.print(".");
		}
		Serial.print("\n\tGot wireless IP: ");
		Serial.println(WiFi.localIP());
	#endif
} // setupNetwork

/*Function that returns data for Azure
	User can customize this funtion to his needs
	--> this is just for demonstration
	--> JSON string with unique device ID (based on MAC) & some random data
*/
String buildPayload() {
  char prefixedMac[3 + 1 + 6 + 1];	//prefix of 3 characters, 1 dash, 6 hex values of MAC and 1  terminating character
  ssidPrefixMac(&prefixedMac[0], "IoT");  //create unique device name
  String json = "{\"device\":\""    + (String)prefixedMac +
                "\",\"timestamp\":\"" + time(nullptr) +
                "\",\"rand1\":\"" + random(1, 100000) +
                "\",\"rand2\":\"" + random(1, 100000) +
                "\"}";
  return json;
} // buildPayload

void setup() {
	Serial.begin(115200);	//debug the needed things on serial port
	while (!Serial);		//is this needed? 
	Serial.println("\r\nPWR:\tBooting ESP");
	//provide noise to the random generator --> can be left out
	#if defined(ARDUINO_ARCH_ESP8266)
		randomSeed(analogRead(A0));
	#elif defined(ARDUINO_ARCH_ESP32)
		randomSeed(analogRead(36));
	#endif
	//set a digital output to demonstrate C2D (Cloud To Device)
	pinMode(DBG_PIN, OUTPUT);
	digitalWrite(DBG_PIN, LOW); //change to default state when power on
	//setup network depending on needs (wired/wireless)
	setupNetwork();
} // setup

//two timeout counters for C2D and D2C
uint32_t lastCheckC2D, lastCheckD2C;

void loop() {
	String methodName, payload;
	AZURE_REP reply;
	#if defined USE_LAN && USE_LAN == true
		while(Ethernet.linkStatus() == LinkOFF)
			if(wiredStatus==DHCP){
				//lost connection
				Serial.println("ETH:\tEthernet cable disconnected.");
				wiredStatus = CABLE_DISCONNECTED;
			}
		}
		if(wiredStatus==DHCP){
			Ethernet.maintain();  //maintain DHCP lease for wired ethernet
		}else{
			if(wiredStatus==CABLE_DISCONNECTED){
				//linked again
				Serial.print("\tRequesting IP");
				while (!Ethernet.begin(macAddr, 1000, 1000)){
					Serial.print(".");
				}
				//passed DHCP init, so IP received
				wiredStatus = DHCP;
				Serial.print("\n\tGot wired IP: ");
				Serial.println(Ethernet.localIP());
			}else{
				//can we ever come here?
			}
		}
	#else
		//maintain DHCP lease for WiFi?
		yield();
		//check if wifi is disconnected
		if (WiFi.status() != WL_CONNECTED) {
			WiFi.reconnect();
		}
	#endif
	if (lastCheckC2D > millis()) { //48-days overflow check of timer
		lastCheckC2D = millis();
	}
	if (lastCheckD2C > millis()) { //48-days overflow check of timer
		lastCheckD2C = millis();
	}
	azure.worker();	//check for problems (SAS renew, ...)
	//start with time
	if (ntpWorker() == SYNCHRONIZED) {
		//we are only able to do communication if time is correct
		if (!azure.isConnected()) {
			azure.setSasExpiry((uint16_t)SAS_RENEW);
			//azure is not connected/initalized
			#if defined IOT_CENTRAL && IOT_CENTRAL  == true
				//use function overloading
				azure.initAzure(SCOPE_ID, DEVICE_ID, DEVICE_KEY); //do or retry
			#else
				//use function overloading
				azure.initAzure(primaireVerbindingsreeks); //do or retry
			#endif
		} else {
			//azure is connected, we are able to transmit/receive messages
			if ((lastCheckD2C + (IOT_UPDATE * 1000) < millis()) || (lastCheckD2C == 0)) {
				Serial.println("MAIN:\tSending message... ");
				payload = buildPayload();
				reply = azure.send(payload); //Send to azure
				if (reply == AOK || reply == OK_EMPTY) {
					Serial.println("\ttransmit succeeded");
					lastCheckD2C = millis();
				} else {
					Serial.print("\terror! (");
					switch (reply) {  //you can create a custom message for every reply you got
						case CLOCK_NOT_SET:	Serial.print("Clock has not been set.");
											break;
						case TLS_ERROR:		Serial.print("TLS could not be established.");
											break;
						case DPS_ERROR:		Serial.print("DPS has failed.");
											break;
						case UNAUTH:		//Unauthorized
											Serial.print("Server failed to authenticate the request.");
											break;
						case BAD_REQUEST:	//bad request
											Serial.print("Bad format and/or request.");
											break;
						case FORBIDDEN:		//forbidden
											Serial.print("Forbidden.");
											break;
						case UNKNOWN:		Serial.print("Got an unknown reply.");
											break;
						default:			//none of the above
											Serial.printf("%u - huh?", reply);
											break;
					}
					Serial.println(")");
					//create 5 seconds wait to prevent overloading the service
					if (millis() < ((IOT_UPDATE * 1000) - 5000)) {
						delay(5000); //use delay, because unable to make subtraction
					} else {
						lastCheckD2C = millis() - ((IOT_UPDATE * 1000) + 5000);
					}
				}
			}
			//once every POLL_TIME
			if (lastCheckC2D + (POLL_TIME * 1000) < millis()) {
				Serial.println("MAIN:\tChecking for new message... ");
				reply = azure.receive(methodName, payload);
				if (reply == AOK) { //there was data
					Serial.printf("MAIN:\tmethodName: %s, payload: %s\r\n", methodName.c_str(), payload.c_str());
					if (methodName == "ledOn") {
						Serial.println("\tturning LED on");
						digitalWrite(DBG_PIN, HIGH); //change to default state when power on
					}
					if (methodName == "ledOff") {
						Serial.println("\tturning LED off");
						digitalWrite(DBG_PIN, LOW); //change to default state when power on
					}
				} else {
					Serial.println("\tqueue empty");
				}
				lastCheckC2D = millis();
			}
		}//azure.isConnected
	}//ntpWorker==SYNCHRONIZED
} // loop
```
## Python op raspberry pi

In het voorbeeld sturen we data door met een Raspberry Pi (thing)
naar Azure IOT-Central. Eveneens sturen we vanop het dashboard in Azure IoT-Central een actuator aan op de Raspbery Pi.

![figuur](./assets/IoThubRaspberryPi.png)

Bron: Dieter De Preester docent HoWest MCT

## Installatie Azure-iot-device

Installeer op de raspberry pi met pip3 de azure-iot-device lib.

```cmd
            pip3 install azure-iot-device
```

![figuur](./assets/111c7ae4a7e3c9213cb67994980e9729.png)

De gegevens van het apparaat zijn te vinden in IoT-Central onder « Verbinding
met »:

![figuur](./assets/a959263696de15863df868ee3a3b996d.png)

Vul het « id-bereik », de « Apparaat-id » en de « primaire sleutel » in de
arduino code in.

![figuur](./assets/abbd1b0a8031e536c1ba65db33a22d13.png)

In het voorbeeldprogramma wordt een random temperatuur en een random luchtvochtig doorgezonden. Indien
je andere waardes wil doorsturen in een praktische toepassing pas je volgende
stukje code aan:

```python
            temp = random.randint(0, 100)
            vocht = random.randint(0,100)
            data = {"temperatuur" :  temp, "luchtvochtigheid" : vocht }
```

Een actuator (led verbonden met GPIO pin 18) op de raspberry pi aansturen via het dashboard is mogelijk met volgende code

```python
    if method_request.name == "ledOn":
        print("Led On")
        led.on()
    elif method_request.name =="ledOff":
        print ("Led Off")
        led.off()
    else:
        print("Received unknown method: " + method_request.name)
```


De totale code:

```python
import asyncio
import os
from azure.iot.device.aio import IoTHubDeviceClient, ProvisioningDeviceClient
from azure.iot.device import MethodResponse
 
import random
import json

import gpiozero as io

led = io.LED(18)

id_scope = ''
device_id = ''
primary_key = ''

# Declare the device client so it can be used from all the function
device_client = None

# Provisions the device with the Azure device provisioning service or returns
# the connection details if the device is already provisioned
async def register_device():
    provisioning_device_client = ProvisioningDeviceClient.create_from_symmetric_key(
        provisioning_host='global.azure-devices-provisioning.net',
        registration_id=device_id,
        id_scope=id_scope,
        symmetric_key=primary_key,
    )

    return await provisioning_device_client.register()


async def property_handler(patch):
    print("Patch received:", patch)

async def command_handler(method_request):
    print("Message received:", method_request.name)
    print("Message payload:", method_request.payload)

    # Determine how to respond to the command based on the IoT Hub direct method method name
    # which is the same as the IoT Central command name
    if method_request.name == "ledOn":
        print("Led On")
        led.on()
    elif method_request.name =="ledOff":
        print ("Led Off")
        led.off()
    else:
        print("Received unknown method: " + method_request.name)

    # Method calls have to return a response so IoT Central knows it was handled correctly,
    # So send a 200 response to show we handled this
    payload = {"result": True}
    status = 200

    # Send the response
    method_response = MethodResponse.create_from_method_request(method_request, status, payload)
    await device_client.send_method_response(method_response)

# The main async function that runs the app
async def main():
    global device_client
    
    # Regsiter the Pi as an IoT device in IoT Central
    registration_result = await register_device()

    # Build the IoT Hub connection string from the registration details
    # IoT Central sits on top of IoT Hub, and the Python SDK only supports IoT Hub,
    # So to talk to IoT central the IoT Hub connection string needs to be built from details
    # from registering the device with the provisioning service
    conn_str='HostName=' + registration_result.registration_state.assigned_hub + \
                ';DeviceId=' + device_id + \
                ';SharedAccessKey=' + primary_key

    # The client object is used to interact with your Azure IoT Central app via IoT Hub, so create this 
    # from the connection string
    device_client = IoTHubDeviceClient.create_from_connection_string(conn_str)

    # Connect the client to IoT Hub
    print('Connecting')
    await device_client.connect()
    print('Connected')

    # IoT Central stores properties in the device twin, so read this to see if we have a color
    # stored from the last run for the lights. This way when the device starts up it can set the color
    # to the last setting
 

 

    # Set the method request handler on the client to handle IoT Central commands
    device_client.on_method_request_received = command_handler

    # Handle updates to the color property from IoT Central
    device_client.on_twin_desired_properties_patch_received = property_handler

    # Define a message loop that keeps the app alive whilst listening for commands
    async def main_loop():
        while True:
            temp = random.randint(0, 100)
            vocht = random.randint(0,100)
            data = {"temperatuur" :  temp, "luchtvochtigheid" : vocht }
            await device_client.send_message(json.dumps(data))
            print(json.dumps(data))
            await asyncio.sleep(5)

    # Wait for user to indicate they are done listening for method calls
    await main_loop()

    # Finally, disconnect
    await device_client.disconnect()

# Start the async app running
if __name__ == "__main__":
    asyncio.run(main())
```

## Node red

In onderstaande voorbeeld wordt:

-   data (temperatuur, luchtvochtigheid en luchtdruk) afkomstig van het sense
    HAT bord verzonden vanuit node red op een rapsberry pi naar IoT Central.
-   De leds op het sense HAT bediend vanuit het IoT-Central dashboard

![figuur](./assets/IoThubRaspberryPi.png)
![figuur](./assets/619de9b9928d99030229eaaf8f9cae1f.png)
![figuur](./assets/5dbc26e1f3d6d92aeb846cc40d746baa.png)

De uitwerking is gebaseerd op volgende document
<https://pietrobrambati.blog/2020/08/21/sending-commands-from-azure-iot-central-to-raspberry-pi-with-sense-hat-in-node-red/>

## Installatie node-red

Installeer indien nodig node-red op de raspberry pi.
<https://nodered.org/docs/getting-started/raspberrypi>

Open node-red via de browser door het IP-adres en de poort 1880 in de browser in
te voeren:


## Importeren van modules in node red

Voeg de bibliotheek voor azure-iot-central toe. Klik op de 3 horizontale strepen
rechtsboven en kies “Settings” ![figuur](./assets/b397366062b4f04d946f19471df419c1.png)

Kies “Palette” in de user Settings en vervolgens het tabblad “Install”

![figuur](./assets/5e219896ae2adb2a4be05192587c5e2d.png)

Geef bij “search modules” “Iot-Central” in klik op “install” bij
node-red-contrib-azure-iot-central.

![figuur](./assets/3177b1c6a198589ca4d3ac1836d2c715.png)

Klik terug op Install.

![figuur](./assets/e05b643e5535f105ae125b715306c70e.png)

Voeg de bibliotheek voor azure-iot-central toe. Klik op de 3 horizontale strepen
rechtsboven en kies “Settings” ![figuur](./assets/b397366062b4f04d946f19471df419c1.png)

Kies “Palette” in de user Settings en vervolgens het tabblad “Install”

![figuur](./assets/5e219896ae2adb2a4be05192587c5e2d.png)

Geef bij “search modules” “Sensehat” in klik op “install” bij
node-red-pi-sense-hat.

![figuur](./assets/964d4bfa84d46dbeb9f7860e360beb7a.png)

Klik terug op Install.

![figuur](./assets/a150d913932cccb87e60dbbf782a43f3.png)

Kies import in node-red.

![figuur](./assets/52d0dd148a25a756857d7d3866249f1b.png)

Kopieer de json string van
<https://github.com/pietrobr/node-red-contrib-azure-iot-central/blob/master/samples/flow%20SenseHAT%20commands.json>

![figuur](./assets/e41a6407ed200ae6d61875d95741014f.png)

Plaats de json string in node red en klik op “Import”.

![figuur](./assets/32928cb8782172fab729e2c2aa241ee1.png)

## Azure IoT-Central

Maak een nieuw apparaatsjabloon aan met een zelfgekozen naam.

![figuur](./assets/c6368fc57f6c6799fa9baea7fa52274c.png)

Voorzie de interface door op “Aangepast model” te klikken.

![figuur](./assets/718a32f8caa43dd851693b40c04e676f.png)

Vul de weergavenaam en de eenheid in voor:

-   Temperatuur sensor telemetry

-   Humidity sensor telemetry

-   Pressure sensor telemetry

-   turnLedOn bediening actuator Command

-   turnLedOff bediening actuator Command

![figuur](./assets/a79e1ebc7e67ef39be386caa2c004838.png)

![figuur](./assets/f300fa393d6e3e6d276a254f5bcdd049.png)

Klik op “Opslaan”

![figuur](./assets/d5f8b51b34d02399b489ce86e5e73f94.png)

## Visualisatie

Klik op “Het apparaat visualiseren”

![figuur](./assets/fe1f8b2d0451546015849b15a5021a3d.png)

Voeg voor de temperatuur, de luchtdruk en de luchtvochtigheid een tegel toe door
de grootheid te selecteren onder Telemetrie en vervolgens op “Tegel toevoegen”
te klikken.

![figuur](./assets/53877c5198cec68fd6cf26d86fa7b14a.png)

Voeg de bediening toe door bij Opdrachten de bediening te slecteren.

![figuur](./assets/4d97b20f7da5df62d41c8b3237410284.png)

Wanneer alle tegels toegevoegd zijn klik je op “Opslaan” en vervolgens op
“Publiceren”.

![figuur](./assets/1d6e13c7ca304d3182352cbcfddd7c4a.png)

Voeg het device toe door op “+Nieuw” te klikken.

![figuur](./assets/31b801670821900fcfea1eb72c9b88f1.png)

Selecteer het aangemaakte sjabloon.

![figuur](./assets/f6766c26db3c7c4f67dab8d44abb60bb.png)

## Instellingen in node-red

Dubbelklik op

![figuur](./assets/5322e4fa9d21c23b5f327a630b392b27.png)

Vul de Scope ID, Device ID en Primary Key afkomstig van IoT-Central in.

![figuur](./assets/8485ab12ba86c904e82b16ab3750edd7.png)

Pas eventueel de tijd aan om berichten door te sturen.

![figuur](./assets/9c32a337d0a7dada4b3c7615165feca3.png)

## Alarmen instellen

Kies “Regels”

![figuur](./assets/5d71484eed390371a47de2a69af57aa8.png)

Kies om een nieuwe regel in te stellen. Druk op “+Nieuw”

-   Geef de regel een naam.

-   Selecteer het appartaatsjabloon

-   Stel de voorwaarde in

-   Kies een actie

![figuur](./assets/5b1dac18fa7509b086f33d4eeee7f2d5.png)

## Gebruikers

De data kan zichtbaar gemaakt worden voor andere gebruikers. Kies “Beheer” en
vervolgens “Gebruikers”

![figuur](./assets/72504b71b69b3bc029c801ed24debfb2.png)

Klik op “+ Nieuwe gebruiker” vul het email adres in van de gebruiker en kies
zijn rol.

![figuur](./assets/52e803dbf087bd30784a170dc53929ef.png)


## License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.

[![Netlify Status](https://api.netlify.com/api/v1/badges/bca9b289-c9d8-4088-b4ff-2abf728b7685/deploy-status)](https://app.netlify.com/sites/innovet-azure-iot-central/deploys)