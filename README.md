# Format-South-African-mobile-numbers
This php function will format your mobile numbers to the international standard.

```php
function Number_SA($number)
{
    //strip out everything but numbers
    $number =  preg_replace("/[^0-9]/", "", $number);
    //Strip out leading zeros:
    $number = ltrim($number, '0');
    //The default country code
    $default_country_code  = '27';
    //Check if the number doesn't already start with the correct dialling code:
    if ( !preg_match('/^'.$default_country_code.'/', $number)  ) {
        $number = $default_country_code.$number;
    }
    //return the converted number:
    return $number;
}
```
