<table class="tg">

<thead>

<tr>

<th class="tg-uxzq"><span style="font-weight:400;font-style:normal">Sql</span></th>

<th class="tg-uxzq"><span style="font-weight:400;font-style:normal">QuerySet</span></th>

<th class="tg-uxzq"><span style="font-weight:400;font-style:normal">Notes</span></th>

<th class="tg-uxzq">Detail Notes</th>

</tr>

</thead>

<tbody>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> Person;</td>

<td class="tg-35wd">Person.objects.all()</td>

<td class="tg-35wd">Fetch all rows</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> name="Tom";</td>

<td class="tg-35wd">Person.objects.get(name="Tom")</td>

<td class="tg-35wd">get()</td>

<td class="tg-mgi7">https://docs.djangoproject.com/en/3.0/ref/models/querysets/#get  
get() raises MultipleObjectsReturned if more than one object was found.  
The MultipleObjectsReturned exception is an attribute of the model class.  
get() raises a DoesNotExist exception if an object wasn’t found for the given parameters.  
This exception is an attribute of the model class.  
</td>

</tr>

<tr>

<td class="tg-mgi7"></td>

<td class="tg-35wd">bob, created = Person.objects.get_or_create(name="Bob", age=24)</td>

<td class="tg-35wd">get_or_create()</td>

<td class="tg-mgi7">https://docs.djangoproject.com/en/3.0/ref/models/querysets/#get-or-create  
</td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> name, age <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person;</td>

<td class="tg-35wd">Person.objects.only('name', 'age')</td>

<td class="tg-35wd">Fetch specific columns</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> id, name <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person;</td>

<td class="tg-35wd">Blog.objects.values('id', 'name')</td>

<td class="tg-35wd">values()  
Fetch specific columns</td>

<td class="tg-mgi7">https://docs.djangoproject.com/en/3.0/ref/models/querysets/#values  
Returns a QuerySet that returns dictionaries,  
rather than model instances, when used as an iterable.  
<QuerySet [{'id': 1, 'name': 'Tom'}]>  
<QuerySet [{'id_page': 21, 'page_token': 'CAoQAA'},  
{'id_page': 23, 'page_token': 'CB4QAA'}]>  
</td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> id = 1;</td>

<td class="tg-35wd">Person.objects.filter(id=1)</td>

<td class="tg-35wd">filter()  
Filter by single column</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> gender='male' <span style="color:rgb(49, 102, 255)">AND</span> age > 25;</td>

<td class="tg-35wd">Person.objects.filter(gender='male', age__gt=25)</td>

<td class="tg-35wd">AND</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> gender='male' <span style="color:rgb(49, 102, 255)">OR</span> age > 25;</td>

<td class="tg-35wd">Person.objects.filter(Q(gender='male') | Q(age__gt=25))</td>

<td class="tg-35wd">OR</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-acfy" colspan="3">IN</td>

<td class="tg-mgi7">https://docs.djangoproject.com/en/3.0/ref/models/querysets/#in  
In a given iterable; often a list, tuple, or queryset.  
It’s not a common use case, but strings (being iterables) are accepted.  
</td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> ... <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> id <span style="color:rgb(49, 102, 255)">IN</span> (1, 3, 4);</td>

<td class="tg-35wd">Entry.objects.filter(id__in=[1, 3, 4])</td>

<td class="tg-mgi7"></td>

<td class="tg-mgi7"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> ... <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> headline <span style="color:rgb(49, 102, 255)">IN</span> ('a', 'b', 'c');</td>

<td class="tg-35wd">Entry.objects.filter(headline__in='abc')</td>

<td class="tg-mgi7"></td>

<td class="tg-mgi7"></td>

</tr>

<tr>

<td class="tg-acfy" colspan="3">COUNT</td>

<td class="tg-mgi7">https://docs.djangoproject.com/en/3.0/ref/models/querysets/#count</td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> count(*) <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit</td>

<td class="tg-35wd">Fruits.objects.count()</td>

<td class="tg-mgi7"></td>

<td class="tg-mgi7"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> count(*) <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> name=’Orange’</td>

<td class="tg-35wd">Fruits.objects.filter(name__exact=’Orange’).count()</td>

<td class="tg-mgi7"></td>

<td class="tg-mgi7"></td>

</tr>

<tr>

<td class="tg-acfy" colspan="3">EXIST</td>

<td class="tg-mgi7">https://docs.djangoproject.com/en/3.0/ref/models/querysets/#exists</td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> (1) AS `a` <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> `person`  
<span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> `person`.`id_person` = 1 <span style="color:rgb(49, 102, 255)">LIMIT</span> 1</td>

<td class="tg-35wd">if Person.objects.filter(pk=1).exists():</td>

<td class="tg-mgi7"></td>

<td class="tg-mgi7">Returns True if the QuerySet contains any results,  
and False if not.  
This tries to perform the query in the simplest and fastest way possible, but it does execute nearly the same query as a normal QuerySet query.</td>

</tr>

<tr>

<td class="tg-acfy" colspan="3">Filter by comparison operators</td>

<td class="tg-wlmb"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> <span style="color:rgb(49, 102, 255)">NOT</span> age=23;</td>

<td class="tg-35wd">Person.objects.exclude(age=23)</td>

<td class="tg-35wd">NOT, !=</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> age > 18;</td>

<td class="tg-35wd">Person.objects.filter(age__gt=18)</td>

<td class="tg-35wd">greater than</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> age >= 18;</td>

<td class="tg-35wd">Person.objects.filter(age__gte=18)</td>

<td class="tg-35wd">greater than or equal-to</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> age < 18;</td>

<td class="tg-35wd">Person.objects.filter(age__lt=18)</td>

<td class="tg-35wd">less than</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> age <= 18;</td>

<td class="tg-35wd">Person.objects.filter(age__lte=18)</td>

<td class="tg-35wd">less than or equal-to</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-mgi7"></td>

<td class="tg-mgi7"></td>

<td class="tg-mgi7"></td>

<td class="tg-mgi7"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> age <span style="color:rgb(49, 102, 255)">BETWEEN</span>10 <span style="color:rgb(49, 102, 255)">AND</span> 20;</td>

<td class="tg-35wd">Person.objects.filter(age__range=(10, 20))</td>

<td class="tg-35wd">BETWEEN</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> name=’Apple’</td>

<td class="tg-35wd">Fruits.objects.filter(name__exact=’Apple’)</td>

<td class="tg-35wd">case sensitive</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> lower(name)=lower(‘Apple’)</td>

<td class="tg-35wd">Fruits.objects.filter(name__iexact=’Apple’)</td>

<td class="tg-35wd">case in-sensitive</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-acfy" colspan="3">LIKE</td>

<td class="tg-wlmb"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> name <span style="color:rgb(49, 102, 255)">LIKE</span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> ‘App%’</td>

<td class="tg-35wd">Fruits.objects.filter(name__startswith=’App’)</td>

<td class="tg-35wd">case sensitive LIKE</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> upper(name) <span style="color:rgb(49, 102, 255)">LIKE</span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> ‘APP%’</td>

<td class="tg-35wd">Fruits.objects.filter(name__istartswith=’app’)</td>

<td class="tg-35wd">case in-sensitive LIKE</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> name <span style="color:rgb(49, 102, 255)">LIKE</span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> ‘%pp%’</td>

<td class="tg-35wd">Fruits.objects.filter(name__contains=’pp’)</td>

<td class="tg-35wd">case sensitive LIKE</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> lower(name) <span style="color:rgb(49, 102, 255)">LIKE</span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> ‘%pp%’</td>

<td class="tg-35wd">Fruits.objects.filter(name__icontains=’pp’)</td>

<td class="tg-35wd">case in-sensitive LIKE</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> name <span style="color:rgb(49, 102, 255)">LIKE</span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> ‘%ple’</td>

<td class="tg-35wd">Fruits.objects.filter(name__endswith=’ple’)</td>

<td class="tg-35wd">case sensitive LIKE</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> lower(name) <span style="color:rgb(49, 102, 255)">LIKE</span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> ‘%ple’</td>

<td class="tg-35wd">Fruits.objects.filter(name__iendswith=’ple’)</td>

<td class="tg-35wd">case in-sensitive LIKE</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-acfy" colspan="3">NULL Values</td>

<td class="tg-wlmb"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> color is <span style="color:rgb(49, 102, 255)">NULL</span></td>

<td class="tg-35wd">Fruits.objects.filter(color__isnull=True)</td>

<td class="tg-35wd">filter by null</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> fruit <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> color is <span style="color:rgb(49, 102, 255)">NOT NULL</span></td>

<td class="tg-35wd">Fruits.objects.filter(color__isnull=False)</td>

<td class="tg-35wd">filter by null</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-acfy" colspan="3">ORDER BY</td>

<td class="tg-wlmb"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)">ORDER BY</span> age;</td>

<td class="tg-35wd">Person.objects.order_by('age')</td>

<td class="tg-35wd">Ascending Order</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> Person <span style="color:rgb(49, 102, 255)">ORDER BY</span> age <span style="color:rgb(49, 102, 255)">DESC</span>;</td>

<td class="tg-35wd">Person.objects.order_by('-age')</td>

<td class="tg-35wd">Descending Order</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-acfy" colspan="3">LIMIT</td>

<td class="tg-mgi7">https://docs.djangoproject.com/en/3.0/topics/db/queries/#limiting-querysets</td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> foo <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> bar <span style="color:rgb(49, 102, 255)">LIMIT</span> 5</td>

<td class="tg-35wd">Entry.objects.all()[:5]</td>

<td class="tg-mgi7"></td>

<td class="tg-mgi7"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> … <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> "auth_user" <span style="color:rgb(49, 102, 255)">LIMIT</span> 10 <span style="color:rgb(49, 102, 255)">OFFSET</span>10</td>

<td class="tg-35wd">Entry.objects.all()[5:10]</td>

<td class="tg-mgi7"></td>

<td class="tg-mgi7"></td>

</tr>

<tr>

<td class="tg-acfy" colspan="3">How to get a single object <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> QuerySet?</td>

<td class="tg-mgi7">https://davit.tech/django-queryset-examples/#section-single-object</td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> … <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> "auth_user" <span style="color:rgb(49, 102, 255)">LIMIT</span> 1</td>

<td class="tg-35wd">User.objects.all()[0]</td>

<td class="tg-35wd">Exception – IndexError</td>

<td class="tg-mgi7"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> … <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> "auth_user" <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> id = 1;</td>

<td class="tg-35wd">User.objects.get(pk=1)</td>

<td class="tg-35wd">Exception – DoesNotExist,  
MultipleObjectsReturned</td>

<td class="tg-mgi7"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> `saved_search_result`  
<span style="color:rgb(49, 102, 255)">ORDER BY</span> `saved_search_result`.`id_saved_search_result`  
ASC <span style="color:rgb(49, 102, 255)">LIMIT</span> 1</td>

<td class="tg-35wd">SavedSearchResult.objects.first()</td>

<td class="tg-mgi7"></td>

<td class="tg-mgi7"></td>

</tr>

<tr>

<td class="tg-acfy" colspan="3">in_bulk()</td>

<td class="tg-mgi7">https://docs.djangoproject.com/en/3.0/ref/models/querysets/#in-bulk  
Метод in_bulk() является более эффективным способом для чтения большого количества записей.  
Он возвращает словарь, то есть объект dict  
</td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> `blog`  
<span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> `blog`.`id_blog` <span style="color:rgb(49, 102, 255)">IN</span> (1)</td>

<td class="tg-35wd">Blog.objects.in_bulk([1])</td>

<td class="tg-35wd">{1: <Blog: Beatles Blog>}</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> `blog`  
<span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> `blog`.`id_blog` <span style="color:rgb(49, 102, 255)">IN</span> (1, 2)</td>

<td class="tg-35wd">Blog.objects.in_bulk([1, 2])</td>

<td class="tg-35wd">{1: <Blog: Beatles Blog>,  
2: <Blog: Cheddar Talk>}</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"></td>

<td class="tg-35wd">Blog.objects.in_bulk([])</td>

<td class="tg-35wd">{}</td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> `blog`  
</td>

<td class="tg-35wd">Blog.objects.in_bulk()</td>

<td class="tg-35wd"></td>

<td class="tg-35wd"></td>

</tr>

<tr>

<td class="tg-35wd"><span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">SELECT</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> * <span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">FROM</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> `blog`  
<span style="color:rgb(49, 102, 255)"><span style="color:rgb(49, 102, 255)">WHERE</span></span> <span style="font-weight:bold;color:rgb(0, 162, 178)"></span> `blog`.`slug` <span style="color:rgb(49, 102, 255)">IN</span> ('beatles_blog')</td>

<td class="tg-35wd">Blog.objects.in_bulk(['beatles_blog'], field_name='slug')</td>

<td class="tg-35wd"></td>

<td class="tg-35wd"></td>

</tr>

</tbody>

</table>