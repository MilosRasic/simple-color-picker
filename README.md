# simpleColorPicker

Extended version simple color picker jQuery plugin by Rachel Carvalho which works with all kinds of elements.

Original plugin at http://github.com/rachel-carvalho/simple-color-picker

Latest version of extended plugin at http://github.com/MilosRasic/simple-color-picker

## New Features and differences

Should work with all kinds of elements instead of only input.
Opens on click instead of focus to work with elements that cannot gain focus.
It is possible to define a callback function which is executed when the user chooses a colour. It gets a reference to the element to which the colorpicker in question is bound and the picked colour represtened with a full hex string (e.g. #ffffff).
On pages with multiple colorpickers, an open colorpicker will close when another one is opened.
May define a custom prefix for colorpicker element id. This is useful for those who don't want to have an id on element(s) to which colorpicker is bound. Not defining the prefix will use original behaviour.

## Usage

Bind the color picker to any element. The color picker will appear when the element is clicked.
Define a change callback function to process user's choice.

### Samples

#### Default options

    $(document).ready(function() {
        $('.color').simpleColorPicker();
    });

#### More colors per line

    $(document).ready(function() {
        $('.color').simpleColorPicker({ colorsPerLine: 16 });
    });

#### Different colors

    $(document).ready(function() {
        var colors = ['#000000', '#444444', '#666666', '#999999', '#cccccc', '#eeeeee', '#f3f3f3', '#ffffff'];
        $('.color').simpleColorPicker({ colors: colors });
    });

#### Effects

    $(document).ready(function() {
        $('.color').simpleColorPicker({ showEffect: 'fade', hideEffect: 'slide' });
    });

#### Callback

    $(document).ready(function() {
        $('.color').simpleColorPicker({
        	change: function(element, color) {
        		element.css('background-color', color);
        	}
        });
    });

#### Custom Prefix

    $(document).ready(function() {
        $('.color').each(function () {
        	$(this).simpleColorPicker({ prefix: $(this).parent().attr('id')+'_' });
       	});
    });