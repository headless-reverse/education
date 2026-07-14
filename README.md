# Zestawienie Struktur Danych i Kanałów Transmisji

---

## 1. Binarny, stały rozmiar

* **Metoda połączenia:** 
  UDP, UART (Serial), SPI, CAN FD
* **Narzędzia / Programy:**
  * **Netcat (nc)** – Wykorzystywany do przesyłania surowych struktur binarnych bezpośrednio na porty sieciowe.
  * **Customowe backdoory / rootkity** – Używają stałych struktur ukrytych w standardowym ruchu UDP, aby utrudnić ich wykrycie w analizie sieciowej.
  * **Customowe bootloadery / roboty** – Zastosowanie niskopoziomowe w celu eliminacji narzutu protokolarnego.
  * **Wireshark** – Analiza i dekodowanie surowych pakietów za pomocą dedykowanych parserów (dissectorów).
  * **Saleae Logic** – Wizualizacja i dekodowanie sygnałów cyfrowych bezpośrednio z magistral SPI, UART czy CAN.

---

## 2. Binarny, zmienny rozmiar

* **Metoda połączenia:** 
  TCP, WebSocket, USB Bulk
* **Narzędzia / Programy:**
  * **ADB (Android Debug Bridge)** – Przesyłanie danych z precyzyjnie określonym rozmiarem pakietu w nagłówkach binarnego protokołu.
  * **Frida (dla inspekcji)** – Monitorowanie dynamicznej komunikacji binarnej w pamięci procesu.
  * **Netcat / ncat (klient/serwer)** – Uniwersalne przesyłanie pakietów o zmiennym rozmiarze przez strumienie TCP.
  * **Wireshark** – Filtrowanie i śledzenie niestandardowych strumieni binarnych o zmiennym rozmiarze pakietu.
  * **Nmap** – Wykrywanie i analiza surowych odpowiedzi serwerów poprzez wysyłanie niestandardowych pakietów binarnych.

---

## 3. TLV (Type-Length-Value)

* **Metoda połączenia:** 
  TCP, BLE, Systemy SmartCard (EMV)
* **Narzędzia / Programy:**
  * **NfcTool / Wireshark** – Służą do przechwytywania i analizy ustrukturyzowanych ramek standardu EMV lub BLE.
  * **OpenSSL (TLV w certyfikatach)** – Format ASN.1 używa struktury TLV do kodowania parametrów kryptograficznych.
  * **SmartCard tools** – Komunikacja z procesorami kart płatniczych i SIM.
  * **Zeek (Bro)** – Analiza ruchu sieciowego potrafiąca interpretować zaawansowane protokoły oparte na strukturach TLV.
  * **Pycrate** – Biblioteka Python używana do automatycznego generowania i parsowania struktur ASN.1/TLV.

---

## 4. Strukturalny Tekst (JSON / XML)

* **Metoda połączenia:** 
  HTTP / HTTPS, REST API, WebSockets
* **Narzędzia / Programy:**
  * **Postman / Insomnia** – Środowiska programistyczne dedykowane do wywoływania i testowania API tekstowych.
  * **Burp Suite / OWASP ZAP** – Analiza i manipulacja strukturami JSON/XML przechodzącymi przez proxy.
  * **curl / httpie** – Konsolowe narzędzia do wysyłania ustrukturyzowanych zapytań HTTP.
  * **jq** – Niezastąpione narzędzie wiersza poleceń do filtrowania, modyfikowania i formatowania danych JSON.
  * **yq** – Konsolowy procesor do obsługi plików YAML, XML oraz JSON.
  * **Bruno** – Nowoczesny, lekki i otwartoźródłowy klient do testowania API przechowujący kolekcje w czystym tekście.

---

## 5. Protobuf / FlatBuffers

* **Metoda połączenia:** 
  gRPC (HTTP/2), TCP, IPC
* **Narzędzia / Programy:**
  * **gRPC / Protoc** – Kompilacja schematów i obsługa silnie typowanych wywołań RPC.
  * **FlatBuffers / flexbuffers** – Dostęp do danych bez konieczności kosztownego rozpakowywania całego pakietu.
  * **Narzędzia Google** – Szerokie spektrum bibliotek diagnostycznych dla struktur zserializowanych.
  * **Buf** – Nowoczesny zestaw narzędzi (linter, formatter, rejestr) usprawniający pracę ze schematami Protobuf.
  * **mitmproxy** – Zaawansowane proxy posiadające natywne wsparcie dla przechwytywania i dekodowania wiadomości Protobuf.

---

## 6. Strumieniowy (Stream / Pipe)

* **Metoda połączenia:** 
  TCP Stream, Named Pipes, FIFO
* **Narzędzia / Programy:**
  * **ffmpeg / GStreamer** – Przetwarzanie i przesyłanie strumieni audio/wideo w czasie rzeczywistym.
  * **netcat / socat** – Przekierowywanie surowych potoków wejścia/wyjścia przez gniazda sieciowe.
  * **Wireshark (analiza strumienia)** – Rekonstrukcja sesji TCP w spójną całość bez podziału na pakiety fizyczne.
  * **VLC** – Odtwarzacz multimedialny zdolny do odbierania i renderowania różnorodnych sieciowych strumieni transmisji.
  * **OBS Studio** – Pakiet oprogramowania służący do przechwytywania obrazu i wypychania strumieni wideo w czasie rzeczywistym.
  * **Kafka Console Consumer/Producer** – Konsolowe narzędzia do bezpośredniego pobierania i wysyłania ciągłych zdarzeń strumieniowych.

---

## 7. Bezpieczeństwo / Szyfrowanie

* **Metoda połączenia:** 
  TLS, DTLS, SSH, IPsec
* **Narzędzia / Programy:**
  * **OpenSSL / LibreSSL** – Zarządzanie certyfikatami, testowanie i wdrażanie bezpiecznych kanałów TLS.
  * **WireGuard / SSH** – Implementacja zaszyfrowanych tuneli na poziomie sieciowym i transportowym.
  * **Wireshark (analiza TLS)** – Deszyfrowanie zabezpieczonych potoków po dostarczeniu kluczy sesyjnych.
  * **GnuPG (GPG)** – Narzędzie do szyfrowania i podpisywania danych w spoczynku lub w asynchronicznym transporcie.
  * **HashiCorp Vault** – Scentralizowany system zarządzania sekretami, kluczami szyfrującymi i certyfikatami.
  * **Nmap** – Możliwość audytu kryptograficznego poprzez skanowanie wspieranych algorytmów (ciphers) serwera.

---

## 8. Modularny / Plugin / Rozszerzalny

* **Metoda połączenia:** 
  IPC, gRPC, Plugin API
* **Narzędzia / Programy:**
  * **Systemy plugin (GIMP, VS Code)** – Dynamiczne dołączanie funkcjonalności za pomocą ściśle określonych interfejsów API.
  * **D-Bus / gRPC** – Znormalizowane szyny komunikacji do wymiany informacji między niezależnymi modułami.
  * **Frida (moduły)** – Wstrzykiwanie własnych skryptów i rozszerzeń do działających procesów.

---

## 9. Kolumnowy (Columnar Storage)

* **Metoda połączenia:** 
  Przesył plików (S3, HDFS), TCP
* **Narzędzia / Programy:**
  * **Apache Spark** – Silnik przetwarzania danych masowych zoptymalizowany pod kątem formatów kolumnowych.
  * **DuckDB** – Wbudowana, zorientowana kolumnowo baza danych dedykowana dla szybkich zapytań analitycznych SQL.
  * **Pandas** – Biblioteka Python przetwarzająca ramki danych w modelu kolumnowym bezpośrednio w pamięci RAM.
  * **Apache Arrow** – Platforma ujednolicająca reprezentację danych w pamięci do błyskawicznych operacji kolumnowych.

---

## 10. Log sekwencyjny (Write-Ahead Log)

* **Metoda połączenia:** 
  TCP, gRPC, Kafka Protocol
* **Narzędzia / Programy:**
  * **Apache Kafka** – Rozproszony system przesyłania strumieni oparty o partycjonowany log sekwencyjny.
  * **Redpanda** – Wydajna, zgodna z protokołem Kafki platforma strumieniowa napisana w C++.
  * **PostgreSQL / SQLite (WAL)** – Wykorzystanie logów WAL do odtworzenia transakcji bazy w przypadku awarii.

---

## 11. Samoopisujący binarny (CBOR / MsgPack)

* **Metoda połączenia:** 
  HTTP/2, WebSockets, CoAP (dla IoT)
* **Narzędzia / Programy:**
  * **Biblioteki MessagePack** – Wsparcie w większości języków dla natychmiastowej serializacji obiektów do binarnego JSON.
  * **CoAP tools** – Praca z protokołem CoAP dedykowanym dla IoT, który natywnie korzysta z formatu CBOR.
  * **Redis** – Często przechowuje złożone struktury obiektowe zserializowane za pomocą MessagePack w celu oszczędności pamięci.
