---
layout: home
---

<div id="aboutme">
    <h1>Qiwihui's Page</h1>

    <p>I am Chris Qiu, usually I use Qiwihui as my alias. Here is my page. I graduated from <a href="http://www.buct.edu.cn/">BUCT</a>, and I majored in Information and Computation Science.</p>

    <dl>
        <dt><strong> Contact me: </strong></dt>
        <dd> Email: qwh005007 AT gmail.com
        <dd> github: <a href="https://github.com/Qiwihui">@Qiwihui</a>
    </dl>
    <hr>
</div>

<div id="blog">
    <div id="section">
        <p>
        [ <a href="/content/MathTalking">MathTalking</a> |
         <a href="/content/ProgramThinking">ProgramThinking</a> |
         <a href="/content/HereLife">HereLife</a> ]
        </p>

        <h2 id="mathtalking">Math Talking</h2>
        <p>Something about math. Math is very beautiful, useful and powerful, I think i will never hate it.</p>
        <ul>
        {% for post in site.categories.mathtalking %}
            <li> - <a href="{{ post.url }}">{{ post.title }}</a></li>
                <div>{{ post.description }}</div>
            </li>
        {% endfor %}
        </ul>

        <h2 id="programthinking">Program Thinking</h2>
        <p>Program can help you do many things effectively, not only in work, also in life. And programatic think helps a lot.</p>
        <ul>
        {% for post in site.categories.programthinking %}
            <li> - <a href="{{ post.url }}">{{ post.title }}</a></li>
                <div>{{ post.description }}</div>
            </li>
        {% endfor %}
        </ul>

        <h2 id="herelife">Here Life</h2>
        <p>My life, my plan, reading, and some other things. Maybe it will contain messy things here. </p>
        <ul>
        {% for post in site.categories.herelife %}
            <li> - <a href="{{ post.url }}">{{ post.title }}</a></li>
                <div>{{ post.description }}</div>
            </li>
        {% endfor %}
        </ul>

    </div>
    <p>Copyright &copy; 2014, <a href="mailto:qwh005007@gmail.com">Qiwihui</a>.</p>
</div>