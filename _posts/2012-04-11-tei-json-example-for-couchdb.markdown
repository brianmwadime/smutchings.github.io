---
layout: post
title: TEI JSON Example for CouchDB
date: 2012-04-11 12:21:18.000000000 +02:00
---
This is an example of a TEI implementation in JSON for CouchDB. Feel free to use it for your own TEI projects. You can read more about the benefits of JSON and how transcription works on mobile devices in my master thesis <a href="http://patrickheneise.me/my-master-thesis" title="My Master Thesis">"A Modern Approach to the Transcription of Vintage Literature using Mobile Technology and Cloud Services"</a>

<code><pre>
{
   "header": {
       "sourceDesc": {
           "biblFull": {
               "titleStmt": {
                   "author": {
                       "key": "BLYT",
                       "name": "Lord Lytton, Edward G.D. Bulwer Lytton (1803-1873)"
                   },
                   "title": "Letter from De Erven F. Bohn to Ouida, 1882-1884: A machine-readable transcription",
                   "summary": "De Erven F. Bohn informs Ouida of that he will send a copy of the Dutch translation of her book by bookpost.",
                   "type": "letter",
                   "recipient": {
                       "key": "OUID",
                       "name": "Ouida"
                   },
                   "date": {
                       "format": "dd-MM-yyyy",
                       "value": "01-01-1882"
                   }
               },
               "publicationStmt": {
                   "idno": [
                       {
                           "content": "BOH C 7, fol. 133",
                           "type": "callNo"
                       }
                   ]
               }
           }
       },
       "publicationStmt": {
           "availability": "Publicly accessiblenn&copy; Copyright 2007, Leiden University",
           "pubPlace": "Leiden, Netherlands",
           "publisher": "Universiteit Leiden (University of Leiden)",
           "date": "2007",
           "address": [
               {
                   "addrLine": "P.O. Box 9515"
               },
               {
                   "addrLine": "2300 RA Leiden"
               }
           ],
           "idno": [
               {
                   "content": "BOH C 7, fol. 133",
                   "type": "callNo"
               }
           ]
       },
       "profileDesc": [
           {
               "textClass": [
                   {
                       "keywords": [
                           {
                               "term": "Nonfiction"
                           },
                           {
                               "term": "Prose"
                           },
                           {
                               "term": "Masculine"
                           }
                       ],
                       "scheme": "http://www.bookstudies.leidenuniv.nl/"
                   }
               ],
               "langUsage": [
                   {
                       "language": "English",
                       "ident": "en-GB",
                       "usage": "100"
                   }
               ]
           }
       ],
       "fileDesc": {
           "titleStmt": {
               "type": "[electronic resource]",
               "principal": "Adriaan van der Weel"
           }
       },
       "encodingDesc": {
           "projectDesc": "Prepared by students of the 2007-2008 Digital Media Technology course, Book and Digital Media Studies, University of Leiden"
       }
   },
   "references": [
       {
           "attribute": "title",
           "content": "In Maremma"
       },
       {
           "attribute": "abbr",
           "key": "Yrs",
           "content": "Yours faithfully"
       },
       {
           "content": "Lorem ipsum dolor sit er elit lamet, consectetaur cillium adipisicing pecu, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Nam liber te conscient to factor tum poen legum odioque civiuda.",
           "key": "",
           "attribute": "recipient"
       }
   ],
   "annotations": [
       {
           "author": "Patrick Heneise",
           "title": "Hello World",
           "content": "Just a test",
           "category": "Nonsense"
       }
   ],
   "transcription": {
       "closer": {
           "salute": "We remain, dear miss {{1}}",
           "signature": "Messrs De Erven F. Bohn"
       },
       "opener": {
           "salute": "Dear miss!",
           "dateline": {
               "name": {
                   "content": "Haarlem",
                   "type": "place"
               },
               "date": {
                   "content": "1882-1884"
               }
           }
       },
       "text": "Answering to the conditions made for the Dutch translations of {{0}} {{1}} we have the pleasure to send you by bookprint a copy of our translation.[[0]]nnAnother paragraph"
   },
   "images": [
       {
           "url": "http://dl.dropbox.com/u/634149/bol133.jpeg"
       },
       {
           "url": "http://dl.dropbox.com/u/634149/BOHC3_fol254.jpg"
       }
   ],
   "predecessor": "",
   "successor": "",
   "history": [
       {
           "timestamp": "11-07-28 7:40 PM",
           "name": "Patrick Heneise",
           "description": "Edited Transcription"
       },
       {
           "timestamp": "11-07-28 10:17 PM",
           "name": "Patrick Heneise",
           "description": "Edited Metadata"
       }
   ],
   "_attachments": {
       "preview.jpg": {
           "content_type": "image/jpeg",
           "revpos": 10,
           "digest": "md5-fXBVqj7c4K1tXJuMxx1E/Q==",
           "length": 77446,
           "stub": true
       }
   }
}
</pre></code>
