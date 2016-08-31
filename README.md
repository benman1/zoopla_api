# Zoopla Python API

```python
import os

from zoopla.api import ZooplaQuery, ListingStatus

os.environ['ZOOPLA_API_KEY'] = '[API_KEY_GOES_HERE]'

fields = ['listing_id', 'num_bedrooms', 'num_bathrooms', 'image_url',
          'price', 'property_type', 'street_name', 'short_description',
          'last_published_date', 'latitude', 'longitude', 'num_recepts',
          'first_published_date', 'agent_name', 'agent_phone', 'new_home',
          'post_town', 'displayable_address', 'county', 'price_change']


for prop in ZooplaQuery.select(fields, page_number=1, number_of_items=99, property_type='flats', minimum_beds=2, maximum_beds=3, area=city, listing_status=ListingStatus.rent):
    for f in prop:
        print('{}: {}'.format(f, prop[f]))
    print('\n')
```

[Zoopla API official documentation](http://developer.zoopla.com/docs)