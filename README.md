# Geolombia

[![Build Status](https://secure.travis-ci.org/andmej/geolombia.png?branch=master)](http://travis-ci.org/andmej/geolombia)

Geolombia is a gem that has a list of all cities and states in Colombia.

## Installation

Add this line to your application's Gemfile:

    gem 'geolombia'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install geolombia
    
## Documentation

This README is all the documentation I've written so far.

## Usage

    Geolombia::State.find_by_name("Antioquia")
    # => #<Geolombia::State:0x00000100841240 @code="05", @name="Antioquia", @latitude=7.0, @longitude=-75.5>
    
    Geolombia::State.find_by_name("Antioquia").cities
    # => Array of the 125 cities in Antioquia
    
    Geolombia::State.all
    # => Array of the 32 states in Colombia
    
    Geolombia::City.find_by_name("Medellín")
    # => #<Geolombia::City:0x00000100a601e8 @code="05001", @name="Medellín", @state_code="05", @state_name="Antioquia", @latitude=6.2913889, @longitude=-75.5361111>

    Geolombia::City.find_by_name("Medellín").state
    # => #<Geolombia::State:0x00000100842c80 @code="05", @name="Antioquia", @latitude=7.0, @longitude=-75.5> 
    
    Geolombia::City.all
    # => Array of the 1102 cities in Colombia

## Future Usage

    Geolombia::City.where(:name => "Medellín").first

    Geolombia::State.where(:name => "Antioquia").first.cities

    Geolombia::City.first.state

## Compatibility

This gem is currently only compatible with Ruby 1.9.3 and 2.0.0.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Credits

Thanks to Jorge Iván Meza for his [CSV data files](http://blog.jorgeivanmeza.com/2008/09/departamentos-y-municipios-de-colombia-actualizacion-20080915/)    .
