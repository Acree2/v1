javascript:(function HighlightIncomingVillages(){
    try{
        // Skonfiguruj listę koordynatów, które chcesz podświetlić
        var targetCoords = [
            "676|456",  // przykładowe koordynaty wiosek
            "696|490",
            "502|502"
        ];
        
        var _name = 'Incoming Village Highlighter';
        var _win = (window.main || self), $ = _win.$;

        // Sprawdzenie, czy jesteśmy w zakładce Przychodzących ataków
        if(_win.game_data.mode !== 'incomings'){
            alert("Ten skrypt musi być uruchomiony w zakładce Przychodzących ataków (Overviews -> Incoming).");
            return;
        }

        // Debugowanie: informacja o rozpoczęciu skanowania
        console.log("Rozpoczęcie skanowania elementów na stronie.");

        // Przeszukiwanie całego widocznego tekstu na stronie
        $('body *').each(function(){
            var elementText = $(this).text();

            // Debugowanie: pokazanie tekstu elementu
            console.log("Sprawdzany tekst elementu: " + elementText);

            targetCoords.forEach(function(coord){
                if(elementText.indexOf(coord) !== -1){
                    // Debugowanie: pokazanie, które koordynaty zostały znalezione
                    console.log("Koordynaty znalezione w elemencie: " + coord);

                    $(this).css('background-color', 'red');  // Podświetlanie elementów, które zawierają koordynaty
                }
            }.bind(this));  // Zapewniamy, że kontekst "this" odnosi się do elementu
        });
        
        alert("Podświetlanie wiosek zakończone.");
    }
    catch(error){
        alert('Wystąpił błąd: ' + error.message);
        console.error(error);
    }
})();
