# PROJECT TITLE

 project consist of how a pdf can be seen as an in app browser.



# DESCRIPTION

angular project consist of a view that describes how a pdf can be viewed as in-app browser using <i-frame> & creating a pipe that helps in making the url bind with the UI by passing it through the safeResourceUrl.

eg :-

<div *ngIf="dataLocalUrl != undefined">
  <h5>iframe whit local url</h5>
  <iframe width="500" height="600" [src]="dataLocalUrl | safeUrl" type="application/pdf"></iframe>
  <h5>object whit local url</h5>
</div>


pipe :- 

@Pipe({
  name: 'safeUrl'
})
export class SafeUrlPipe implements PipeTransform {

  constructor(private sanitizer: DomSanitizer) { }
  transform(url) {
    return this.sanitizer.bypassSecurityTrustResourceUrl(url);
  }
}


# PdfViewer Hosted

Hosted Link [pdfViewer](http://pdfviewer.surge.sh/)

