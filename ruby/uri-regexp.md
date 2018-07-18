# URI::regexp

## String Match

```ruby
mailto = 'mailto:capollux10@gmail.com'
match_data_mailto = mailto.match(URI::regexp) #=> #<MatchData "mailto:capollux10@gmail.com" 1:"mailto" 2:"capollux10@gmail.com" 3:nil 4:nil 5:nil 6:nil 7:nil 8:nil 9:nil>
puts match_data_mailto[1] #=> "mailto"
puts match_data_mailto[2] #=> "capollux10@gmail.com"

url = 'https://zzulu:123123@zzu.li:80/users/sign_in?form=facebook.com#sign-in-form'
match_data_url = url.match(URI::regexp) #=> #<MatchData "https://zzulu:123123@zzu.li:80/users/sign_in?form=facebook.com#sign-in-form" 1:"https" 2:nil 3:"zzulu:123123" 4:"zzu.li" 5:"80" 6:nil 7:"/users/sign_in" 8:"form=facebook.com" 9:"sign-in-form">
puts match_data_mailto[1] #=> "https"
puts match_data_mailto[3] #=> "zzulu:123123"
puts match_data_mailto[4] #=> "zzu.li"
puts match_data_mailto[5] #=> "80"
puts match_data_mailto[7] #=> "/users/sign_in"
puts match_data_mailto[8] #=> "form=facebook.com"
puts match_data_mailto[9] #=> "sign-in-form"

# 1: scheme, 2: opaque, 3: userinfo, 4: host, 5: port, 6: registry, 7: path, 8: query, 9: fragment

invalid_url = 'this is invalid URL'
match_data_invalid_url = invalid_url.match(URI::regexp) #=> nil
```

## URI.parse

```ruby
mailto = 'mailto:capollux10@gmail.com'
uri_mailto = URI.parse(mailto) #=> #<URI::MailTo mailto:capollux10@gmail.com>
puts uri_mailto.scheme #=> "mailto"
puts uri_mailto.opaque #=> "capollux10@gmail.com"
 
url = 'https://zzulu:123123@zzu.li:80/users/sign_in?form=facebook.com#sign-in-form'
uri_url = URI.parse(url) #=> #<URI::HTTPS https://zzulu:123123@zzu.li:80/users/sign_in?form=facebook.com#sign-in-form>
uri_url.scheme #=> "https"
uri_url.userinfo #=> "zzulu:123123"
uri_url.host #=> "zzu.li"
uri_url.port #=> "80"
uri_url.path #=> "/users/sign_in"
uri_url.query #=> "form=facebook.com"
uri_url.fragment #=> "sign-in-form"

invalid_url = 'this is invalid URL'
uri_invalid_url = URI.parse(invalid_url) #=> URI::InvalidURIError: bad URI(is not URI?)
```

