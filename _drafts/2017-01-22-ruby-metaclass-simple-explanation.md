How I see ruby metaclass
===

When you're working with ruby metaclasses in live code, there's a good chance you'll stumble across this snippet:

metaclass = (class << self; self; end)

Snippet pulled from the beloved [minitest framework](http://yehudakatz.com/2009/11/15/metaprogramming-in-ruby-its-all-about-the-self/).

I saw a few stackoverflow posts on this, and I have a quick and simple explanation of this code.

First, go read this article if you're not familiar with ruby metaclasses: 

[Metaprogramming in Ruby: It's All About the Self](http://yehudakatz.com/2009/11/15/metaprogramming-in-ruby-its-all-about-the-self/)


So let's just use this is a realistic example.

---


module Rural
  mc = (class << self; self; end)

  class Farm

    def initialize(name, animals, address)
      @name    = name || "unnamed"
      @animals = animals || []
      @address = address || "1234 test lane, test state."
    end

    def count_animals
      return @animals.length
    end

    def name
      return @name
    end

    def get_address
      return @address
    end

    private
  end
end


