---
name: test_writer
type: knowledge
version: 1.0.0
agent: CodeActAgent
---

# Test Writer Microagent

Bu microagent, OpenHands projesi için test yazma konusunda rehberlik sağlar.

## Backend Testleri (Python/Pytest)

### Test Dosyası Konumu
- Tüm backend testleri `tests/unit/` dizininde bulunur
- Test dosyaları `test_*.py` formatında adlandırılmalıdır

### Test Çalıştırma
```bash
poetry run pytest tests/unit/test_xxx.py
```

### Test Yazma Kuralları
1. Her test fonksiyonu `test_` ile başlamalıdır
2. Açıklayıcı test isimleri kullanın
3. Her test tek bir davranışı test etmelidir
4. Fixture'ları tekrar kullanılabilir test verisi için kullanın
5. Mock'ları harici bağımlılıkları izole etmek için kullanın

### Örnek Backend Test Yapısı
```python
import pytest
from unittest.mock import Mock, patch

class TestFeatureName:
    """Feature için test sınıfı."""

    def test_should_do_something_when_condition(self):
        """Belirli bir koşulda beklenen davranışı test eder."""
        # Arrange
        input_data = "test"

        # Act
        result = function_under_test(input_data)

        # Assert
        assert result == expected_value

    @pytest.fixture
    def sample_fixture(self):
        """Test için örnek veri sağlar."""
        return {"key": "value"}

    def test_with_fixture(self, sample_fixture):
        """Fixture kullanarak test yapar."""
        assert sample_fixture["key"] == "value"
```

## Frontend Testleri (TypeScript/Vitest)

### Test Dosyası Konumu
- Frontend testleri `frontend/__tests__/` dizininde bulunur
- Test dosyaları `.test.ts` veya `.test.tsx` uzantısı ile adlandırılmalıdır

### Test Çalıştırma
```bash
cd frontend
npm run test
# Belirli bir test çalıştırmak için:
npm run test -- -t "TestName"
```

### Örnek Frontend Test Yapısı
```typescript
import { describe, it, expect, vi } from 'vitest';
import { render, screen } from '@testing-library/react';

describe('ComponentName', () => {
  it('should render correctly', () => {
    render(<ComponentName />);
    expect(screen.getByText('Expected Text')).toBeInTheDocument();
  });

  it('should handle user interaction', async () => {
    const mockHandler = vi.fn();
    render(<ComponentName onClick={mockHandler} />);

    await userEvent.click(screen.getByRole('button'));

    expect(mockHandler).toHaveBeenCalled();
  });
});
```

## Test Yazma En İyi Uygulamaları

1. **AAA Paterni**: Arrange (Hazırla), Act (Uygula), Assert (Doğrula) yapısını kullanın
2. **İzolasyon**: Her test bağımsız olmalı ve diğer testlere bağlı olmamalıdır
3. **Okunabilirlik**: Test isimleri ne test edildiğini açıkça belirtmelidir
4. **Kapsam**: Hem başarılı hem de hata senaryolarını test edin
5. **Edge Cases**: Sınır durumlarını ve edge case'leri test etmeyi unutmayın
6. **Mock Kullanımı**: Harici servisleri ve API çağrılarını mock'layın
