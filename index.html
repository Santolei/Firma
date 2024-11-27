<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carga de firma</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        #firma {
            border: 1px solid #000;
            padding: 10px;
            margin-top: 20px;
            display: none;
            width: 100%;
            max-width: 400px;
        }
    </style>
</head>
<body class="bg-light">
    <div class="container mt-5">
        <h1 class="text-center mb-4">Generar Firma</h1>
        <form id="formulario" class="bg-white p-4 rounded shadow">
            <div class="row g-3 mb-4">
                <div class="col-md-6">
                    <label for="nombre" class="form-label">Nombre:</label>
                    <input type="text" id="nombre" name="nombre" class="form-control" maxlength="25" required>
                </div>
                
                <div class="col-md-6">
                    <label for="matricula" class="form-label">Matrícula:</label>
                    <input type="text" id="matricula" name="matricula" class="form-control" required>
                </div>
                <div class="col-md-6">
                    <label for="cargo" class="form-label">Cargo:</label>
                    <input type="text" id="cargo" name="cargo" class="form-control" maxlength="30" required>
                </div>
                <div class="col-md-6">
                    <label for="interno" class="form-label">Interno:</label>
                    <input type="text" id="interno" name="interno" class="form-control" maxlength="30" required>
                </div>
            </div>
            <div class="text-center">
                <button type="submit" class="btn btn-primary">Generar Firma</button>
            </div>
        </form>

        <div class="row text-center">
            <div id="firma" class="p-3 mt-4 text-center m-auto" style="background: white;"></div>
        </div>
        
        <div class="row text-center mt-3" style="width: 100%; max-width: 400px; margin: auto">
            <a id="descargarBtn" class="btn btn-success mb-3" style="display:none;">Descargar como Imagen</a>     
            <button id="mostrarHtmlBtn" class="btn btn-secondary" style="display:none;" data-bs-toggle="modal" data-bs-target="#modalHtml">Mostrar Código HTML</button>       
        </div>
    </div>

    <!-- Modal para mostrar el código HTML -->
    <div class="modal fade" id="modalHtml" tabindex="-1" aria-labelledby="modalHtmlLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="modalHtmlLabel">Código HTML</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Cerrar"></button>
                </div>
                <div class="modal-body">
                    <textarea id="codigoHtml" class="form-control" rows="10" readonly></textarea>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cerrar</button>
                    <button type="button" class="btn btn-primary" onclick="copiarHtml()">Copiar al Portapapeles</button>
                </div>
            </div>
        </div>
    </div>

    <script>
    document.getElementById('formulario').addEventListener('submit', function(event) {
        event.preventDefault(); // Evita el envío por defecto del formulario

        const nombre = document.getElementById('nombre').value;
        const matricula = document.getElementById('matricula').value;
        const cargo = document.getElementById('cargo').value;
        const interno = document.getElementById('interno').value;

        // Generar la firma solo si los campos están completos
        if (nombre && matricula && cargo && interno) {
            const firmaHtml = `
                <div style="width: 352px">

                    <span style="background: transparent url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAG0AAAA8CAIAAADjSKNTAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyZpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuNi1jMDY3IDc5LjE1Nzc0NywgMjAxNS8wMy8zMC0yMzo0MDo0MiAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENDIDIwMTUgKFdpbmRvd3MpIiB4bXBNTTpJbnN0YW5jZUlEPSJ4bXAuaWlkOjIzMTQ2NDMwMUQ0MTExRTZBODhGRTQ2RUY4REM1MkMzIiB4bXBNTTpEb2N1bWVudElEPSJ4bXAuZGlkOjIzMTQ2NDMxMUQ0MTExRTZBODhGRTQ2RUY4REM1MkMzIj4gPHhtcE1NOkRlcml2ZWRGcm9tIHN0UmVmOmluc3RhbmNlSUQ9InhtcC5paWQ6MjMxNDY0MkUxRDQxMTFFNkE4OEZFNDZFRjhEQzUyQzMiIHN0UmVmOmRvY3VtZW50SUQ9InhtcC5kaWQ6MjMxNDY0MkYxRDQxMTFFNkE4OEZFNDZFRjhEQzUyQzMiLz4gPC9yZGY6RGVzY3JpcHRpb24+IDwvcmRmOlJERj4gPC94OnhtcG1ldGE+IDw/eHBhY2tldCBlbmQ9InIiPz7vW9ZzAAAf0klEQVR42s2c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') no-repeat scroll 0% 0%; display: inline-block; vertical-align: top; padding-right: 6px; width: 109px; height: 60px; margin-bottom: 8px; float: left; margin-right: 4px;"></span>
                    <div style="border-left: 1px solid rgb(0, 107, 167); display: inline-block; vertical-align: top; padding-left: 10px; width: 215px;">
                        
                        <span style="padding: 0px; color: rgb(0, 107, 167); font-style: italic; display: inline-block; font-size: 13px; margin-left: 4px; font-weight: bold; font-family: Verdana; margin-top: 0px;">${nombre}</span>

                        <p style="padding: 0px; margin-left: 4px; display: inline-block; vertical-align: top; width: 100%; margin-top: 0px; color: rgb(0, 0, 0); font-weight: bold; font-size: 10px; font-family: Verdana; line-height: 12px; margin-bottom: 3px;">
                        ${cargo}<br>
                        Matrícula: ${matricula}<br>
                        Tel.: 0810 555 2553 | int.: ${interno}<br>
                        www.sanatorioallende.com
                        </p>

                    </div>

                    <small style="text-align: center; display: inline-block; color: rgb(0, 0, 0); width: 90%; padding: 5px 5% 0px; border-top: 1px solid rgb(0, 107, 167); font-size: 9px; line-height: 13px; font-family: Arial; margin-top: 5px;">
                    El presente e-mail contiene informaci&oacute;n confidencial. 
                    La divulgaci&oacute;n, copia o distribuci&oacute;n est&aacute; prohibida.
                    </small>

                </div>
            `;

            const firmaDiv = document.getElementById('firma');
            firmaDiv.innerHTML = firmaHtml;
            firmaDiv.style.display = 'block';

            // Mostrar botones adicionales
            document.getElementById('descargarBtn').style.display = 'block';
            document.getElementById('mostrarHtmlBtn').style.display = 'block';

            // Generar la imagen de la firma
            html2canvas(firmaDiv).then(canvas => {
                const ctx = canvas.getContext('2d');
                ctx.fillRect(0, 0, canvas.width, canvas.height);

                const imgData = canvas.toDataURL("image/png");
                const downloadLink = document.getElementById('descargarBtn');
                downloadLink.href = imgData;
                downloadLink.download = 'firma.png';
            });

            // Mostrar código HTML en el modal 
            document.getElementById('codigoHtml').value = formatHtml(firmaHtml.trim());
        } else {
            alert('Por favor, completa todos los campos antes de generar la firma.');
        }
    });

    function copiarHtml() {
        const codigoHtml = document.getElementById('codigoHtml');
        codigoHtml.select();
        document.execCommand('copy');
        alert('¡Código HTML copiado al portapapeles!');
    }

    function formatHtml(html) {
        const formattedHtml = html
            .split('\n')
            .map(line => line.trim())
            .join('\n');
        return formattedHtml;
    }
</script>

    <!-- Bootstrap JS y html2canvas -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
</body>
</html>


