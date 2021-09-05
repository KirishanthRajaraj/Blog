---
layout: post
title: M133
---
<!-- 
Next you can update your site name, avatar and other options using the _config.yml file in the root of your repository (shown below).

![_config.yml]({{ site.baseurl }}/images/config.png)

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub. -->
# **M133**

## Session-handling with JSF

### Aufgabenstellung
Ziel dieses Auftrages ist es, mit verschiedenen Input Elementen RGB Werte von 0 bis 255 auswählen zu können und mit diesen Angaben die Hintergrundfarbe der Webseite zu ändern. Ebenfalls muss man wissen welche Session Art zu benutzen ist.


**Ziele:**
* Zur Verwaltung der RGB-Werte eine Backing-Bean Klasse erstellen
* Nutzung von drei verschiedenen Eingabeelementen: inputText, selectOneMenu und selectOneListbox
* Die Hintergrundfarbe der Webseite anhand der Benutzereingaben ändern
* Ich weiss, warum man `@ApplicationScoped` benutzt

### Produkt

Zuerst habe ich eine Backing-Bean Java Klasse erstellt, indem ich die Getter und Setter für die RGB Werte erstellte und die `@ApplicationScoped` Annotation benutzte. `@ApplicationScoped` besagt einfach, dass die Variablen der Applikation so lange gespeichert werden soll, wie die Applikation offen ist.

Auf der index.xhtml Seite habe ich die Eingaben des Benutzers in meine Backing-Bean Klasse zu meinen erstellten Getter und Setter weitergeleitet (siehe Abb.1).

Und weil das ganze ein form ist (siehe Abb. 1), habe ich den Benutzer einfach auf dieselbe Seite weitergeleitet, sodass die Werte übergeben werden und der Hintergrund geändert wird. Für das Umwandeln von rgb zu Hex habe ich eine Methode online gefunden:
<br />

    ```java
    public String rgbToHex(){
        String hex = String.format("#%02x%02x%02x", rgbred, rgbgreen, rgbblue); 
        return hex;
    }
    ```

### Abb. 1

![index.xhtml]({{ site.baseurl }}/images/RGB-indexsite.png)

### Vorschau
[![Vorschau](http://img.youtube.com/vi/sXqKHWvyHwo/0.jpg)](http://www.youtube.com/watch?v=sXqKHWvyHwo)
https://youtu.be/

### Reflexion

Was mich am Anfang sehr verwirrt hat, war die Wertweiterleitung zur Backing-Bean. Warum sagt man z. B. `#{BackingBean.rgbblue)`, statt `#{BackingBean.setrgbblue)` oder `#{BackingBean.getrgbblue)`. Später habe ich gemerkt, dass es den Setter oder Getter nach dem xhtml Elementtyp nimmt. Ob es ein Eingabe- oder Ausgabeelement ist. Bei `<h:inputText>` ist es klar ein Eingabeelement, also wird der Wert an die Setter Methode weitergeleitet. 

Ebenfalls konnte ich die weiteren Input Elemente selectOneMenu und selectOneListbox nicht implementieren. Es war relativ mühsam herauszufinden wie man die Dropdowns mit Items befüllt.

Ansonsten gab es keine grossen Schwierigkeiten, ausser dass man `@ApplicationScoped` benutzen musste, was auch ziemlich selbsterklärend ist.

**Ziele:**
* **Erreicht** Zur Verwaltung der RGB-Werte eine Backing-Bean Klasse erstellen
* **Nicht erreicht** Nutzung von drei verschiedenen Eingabeelementen: inputText, selectOneMenu und selectOneListbox
* **Erreicht** Die Hintergrundfarbe der Webseite anhand der Benutzereingaben ändern
* **Erreicht** Ich weiss, warum man @ApplicationScoped benutzt

### Validierung
Projekt download:
[LA_133_9952_RGBtoHex.zip](https://github.com/KirishanthRajaraj/blog/files/7112462/LA_133_9952_RGBtoHex.zip)






