# flatpickr-Two-Input-Date-Range-JS
flatpickr Two Input Date Range JS (with jQuery)

```javascript
jQuery(document).ready(function($) {
  if( $(".date-range").length ){
        $(".date-range").flatpickr({
            enableTime:!1,
            nextArrow:'<i class="zmdi zmdi-long-arrow-right" />',
            prevArrow:'<i class="zmdi zmdi-long-arrow-left" />',
            dateFormat: 'Y-m-d',
            defaultDate: '',
            mode: "range",
            locale: dateTimePickerLocale[cms_lang_code],
            onOpen: function(selectedDates, dateStr, instance) {
                instance.set('defaultDate', 'today');
            },
            onClose: function(selectedDates, dateStr, instance) {
                if(!dateStr){return false}
                if (dateStr.indexOf(" to ") != -1) {
                    //var SecilenTarih = dateStr.replace(' to ', '|');
                    var SecilenTarih = dateStr.split(' to ');
                        $("#startDate").val(SecilenTarih[0]);
                        $("#endDate").val(SecilenTarih[1]);
                    // var UrlNow = '/'+(location.pathname+location.search).substr(1);
                    //     UrlNow = removeParam('Tarih', UrlNow);
                    // location.href = UrlNow + '&Tarih=' + SecilenTarih;
                }
            }
        });
    }
});
```
