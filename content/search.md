---
title: "Car Search"
date: 2018-10-30T09:36:15-02:00
---

<script
  src="https://code.jquery.com/jquery-3.3.1.min.js"
  integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8="
  crossorigin="anonymous"></script>

<script>
    
    var cache = {};
    
    function load( url ) {

        if( ! cache[ url ] ) {
            cache[ url ] = $.ajax( url );
        }

        return cache[ url ];
    }

    // Taxonomy

    load( '/playground/tags/' ).done( function( response ) {

        var data = $( jQuery.parseHTML( response ) ).find( '.catalogue' ).find( 'li' );
        
        var cars = {};

        $.each( data, function ( offset, current ) {
            
            var url = $( current ).find( 'a' ).attr( 'href' ).replace( /\/?$/, '/' );

            load( url ).done( function( response ) {

                if( ! cars[ url ] ) {

                    var name = $( response ).find( '.post-title' ).text()
                    
                    $( '<p/>', { 'class': name }).html(
                        $( '<a/>', { 'href': url }).attr( 'target', '_blank' ).text( name )
                    ).appendTo( '#results' );

                    cars[ url ] = true;
                }
            });
        });
    });
</script>

<div id="results"></div>