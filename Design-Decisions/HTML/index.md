## HTML

The worst problem that I've found with HTML is that it's so easy to nest everything more layers deep than necessary, and for this fact, it becomes really difficult to read the code.

Your eyes may even start to bleed.

Even worse when each HTML element contains from two to ten attributes, it demotivates a developer from putting in 110% effort to leave things in a better state than he/she found them.

Consider the following code, and just for the sake of simplicity, lets assume Angular is being used:

```HTML

<article *ngFor="let article of articles | async" id="article-12" name="article-12" class="content__article">
    <section id="article-12__header" name="article-12__header" class="article__section section__header">
        <h2>{{article.heading}}</h2>
    </section>

    <section id="article-12__content" name="article-12__content" class="article__section section__content section__content--summarized">
        <p *ngFor="let paragraph of article.paragraphs" class="article__content-paragraph">
            {{paragraph}}
        </p>
    </section>

    <section id="article-12__actions" name="article-12__actions" class="article__footer section__actions">
        <button id="section-12__add-to-favorites" name="section-12__add-to-favorites" class="actions__button button__add-to-favorites" i18n="@@buttonAddToFavorites" (click)="addToFavorites(article)">
            Add to Favorites
        </button>
        <button id="section-12__add-comment" name="section-12__add-comment" class="actions__button button__add-comment" i18n="@@buttonAddComment" (click)="addComment(article)">
            Add a Comment
        </button>
    </section>
</article>

```

That is a simple example of an HTML page which might contain an article being displayed to a user, and the user can then go and add the article to their list of favorites, or they can choose to comment on the article.

We have already made this example so much easier to read by adding [BEM](http://getbem.com/), but we can't expect BEM to do everything for us.

Imagine if there was no BEM, and it was a CSS framework like Bootstrap being used here.

Imagine the scaffolding of the grid in Bootstrap included in that example... Just imagine it.

Terrible, isn't it?

Now look at this example, at how we can possibly clean up the code:

```HTML

<article *ngFor="let article of articles | async" 
         id="article-12" 
         name="article-12"
         class="content__article">

    <section id="article-12__header" 
             name="article-12__header" 
             class="article__section section__header">
        <h2> {{ article.heading }} </h2>
    </section>

    <section id="article-12__content" 
             name="article-12__content" 
             class="article__section section__content section__content--summarized">
        <p *ngFor="let paragraph of article.paragraphs" 
           class="article__content-paragraph">
            {{ paragraph }}
        </p>
    </section>

    <section id="article-12__actions" 
             name="article-12__actions" 
             class="article__footer section__actions">
        <button id="section-12__add-to-favorites" 
                name="section-12__add-to-favorites" 
                class="actions__button button__add-to-favorites" 
                i18n="@@buttonAddToFavorites"
                (click)="addToFavorites(article)">
            Add to Favorites
        </button>

        <button id="section-12__add-comment" 
                name="section-12__add-comment" 
                class="actions__button button__add-comment" 
                i18n="@@buttonAddComment"
                (click)="addComment(article)">
            Add a Comment
        </button>
    </section>

</article>

```

And voila! Just like that, we have code running down the left of the screen instead of from left to right.

Sure it makes the HTML file take up more lines... but who cares, right?

The code will be minified anyway (or it should be), and it makes the HTML code way more readable and maintainable.

I think we can say that this code is LIFT compliant.