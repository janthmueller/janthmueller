---
title: Resume
hide_header: true
---

<object id="pdf-viewer" width="100%" height="600" type="application/pdf"
        data="{{ '/assets/en/resume.pdf#zoom=85&scrollbar=0&toolbar=0&navpanes=0' | relative_url }}">
  <p>Your browser does not support PDFs.
    <a id="pdf-link" href="{{ '/assets/en/resume.pdf' | relative_url }}">Open the PDF</a>.
  </p>
</object>

<div style="text-align: center; margin-top: 10px;">
  <a id="toggle-pdf" onclick="togglePDF()" style="
    color: #1E90FF;
    text-decoration: underline;
    cursor: pointer;
    font-size: 16px;
    margin-right: 15px;">
    Switch to German
  </a>
  <a id="download-pdf" href="{{ '/assets/en/resume.pdf' | relative_url }}" download="resume.pdf" style="
    color: #1E90FF;
    text-decoration: underline;
    cursor: pointer;
    font-size: 16px;">
    Download PDF
  </a>
</div>

<script>
  let isEnglish = true;

  function togglePDF() {
    const pdfViewer = document.getElementById('pdf-viewer');
    const downloadLink = document.getElementById('download-pdf');
    const toggleLink = document.getElementById('toggle-pdf');

    if (isEnglish) {
      pdfViewer.data = "{{ '/assets/de/resume.pdf#zoom=85&scrollbar=0&toolbar=0&navpanes=0' | relative_url }}";
      downloadLink.href = "{{ '/assets/de/resume.pdf' | relative_url }}";
      downloadLink.setAttribute("download", "resume_de.pdf");
      toggleLink.textContent = "Switch to English";
    } else {
      pdfViewer.data = "{{ '/assets/en/resume.pdf#zoom=85&scrollbar=0&toolbar=0&navpanes=0' | relative_url }}";
      downloadLink.href = "{{ '/assets/en/resume.pdf' | relative_url }}";
      downloadLink.setAttribute("download", "resume_en.pdf");
      toggleLink.textContent = "Switch to German";
    }

    isEnglish = !isEnglish;
  }
</script>
