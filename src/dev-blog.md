
```html // 2019.8.12
    <!-- AutofillChaptersList -->

    <script>
        function AutofillChaptersList () {

            // cast
            const listwrap = document.querySelector('.js-for-ChaptersList')
            const chapters = document.querySelectorAll('article.chapter[id]')
            const cssTitle = '.chapter-header>h2'

            // operations
            const createChapterLink = function (pointer, caption) {
                let item = document.createElement('li')
                let link = document.createElement('a')
                let text = caption.textContent || 'undefined'
                link.classList.add('js-for-ChaptersBar')
                link.href = '#' + pointer
                link.textContent = text
                item.appendChild(link)
                listwrap.appendChild(item)
            }
            const doFindAndAddToList = function (el) {
                const pointer = el.id
                const caption = el.querySelector(cssTitle)

                if (pointer && caption) createChapterLink(pointer, caption)
            }

            // autofilling process
            chapters.forEach(doFindAndAddToList)
        }
        //(AutofillChaptersList)()
    </script>
```