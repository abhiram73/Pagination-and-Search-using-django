<form action="" method="GET">
    <input type="saerch" name="movie_name">
    <button type="submit">Search</button>
</form>

{}

{% for movie_item in movie_objects %}
   {{ movie_item.name }}
   <br>
{% endfor %}


{% if movie_objects.has_previous %}

 <a href="?page=1">First</a>
 <a href="?page={{ movie_objects.previous_page_number }}">Previous</a> 

 {% endif %}

 Page: {{ movie_objects.number}} of {{movie_objects.paginator.num_pages}}

 {% if movie_objects.has_next %}
 <a href="?page={{ movie_objects.next_page_number }}">Next</a>
 <a href="?page={{ movie_objects.paginator.num_pages }}">Last</a>
 {% endif %}
