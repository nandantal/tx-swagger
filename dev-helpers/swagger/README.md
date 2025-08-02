# TX-BE API Swagger Documentation

This directory contains comprehensive OpenAPI 3.0.3 specifications for the TX-BE (AI Product Development Assistant) backend API. All files are compatible with SwaggerHub for easy import and collaboration.

## 📁 File Structure

### Individual API Modules
- **`health-api.yaml`** - Health check and system status endpoints
- **`project-management-api.yaml`** - Project CRUD operations and status management  
- **`document-management-api.yaml`** - Document upload, processing, and content retrieval
- **`ai-research-api.yaml`** - AI research phase for market analysis and technical planning
- **`clarification-api.yaml`** - Interactive clarification sessions for requirement gathering
- **`prd-generation-export-api.yaml`** - PRD generation and export functionality
- **`semantic-search-analysis-api.yaml`** - Semantic search and AI-powered content analysis

### Complete Reference
- **`complete-api-reference.yaml`** - Comprehensive API specification combining all endpoints

## 🚀 SwaggerHub Import Instructions

### Option 1: Import Individual Modules
1. Go to [SwaggerHub](https://app.swaggerhub.com)
2. Click "Create New" → "Import and Document API"
3. Choose "File" and upload any of the individual YAML files
4. Each module is self-contained with its own schemas and examples

### Option 2: Import Complete Reference
1. Upload `complete-api-reference.yaml` for the full API specification
2. This provides a unified view of all endpoints with shared components
3. Includes comprehensive authentication, error handling, and response examples

## 📋 API Overview

### Core Features
- **Project Management**: Create, update, and track AI product development projects
- **Document Processing**: Upload and analyze requirement documents with AI
- **AI Research**: Automated market analysis and technical recommendations  
- **Interactive Clarification**: AI-generated questions to gather missing requirements
- **PRD Generation**: Automated creation of comprehensive Product Requirements Documents
- **Architecture Diagrams**: Generated system architecture and data flow diagrams
- **Semantic Search**: Advanced search across all project content and documents
- **Export Options**: Download PRDs in Markdown format with embedded diagrams

### Authentication
```yaml
securitySchemes:
  ApiKeyAuth:
    type: apiKey
    in: header
    name: Authorization
    description: 'API Key authentication. Use: Bearer YOUR_API_KEY'
```

### Rate Limiting
- **Free Tier**: 100 requests per hour
- **Premium Tier**: 1000 requests per hour
- Rate limit headers included in all responses

## 🔧 Usage Examples

### Create a New Project
```bash
POST /api/v1/projects
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json

{
  "productName": "AI Chatbot Platform",
  "productDescription": "SaaS solution for customer support automation",
  "domain": "SaaS",
  "industry": "Customer Support",
  "budgetRange": "$50K - $100K",
  "timeline": "6-9 months",
  "targetMarket": "Small to medium businesses",
  "businessGoals": "Reduce response times and improve satisfaction"
}
```

### Start AI Research
```bash
POST /api/v1/projects/{projectId}/research/start
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json

{
  "researchAreas": ["market_analysis", "technical_requirements", "feature_prioritization"],
  "depth": "comprehensive",
  "includeCompetitorAnalysis": true
}
```

### Generate PRD
```bash
POST /api/v1/projects/{projectId}/generate/prd
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json

{
  "includeArchitectureDiagrams": true,
  "includeTechnicalSpecs": true,
  "includeImplementationRoadmap": true,
  "outputFormat": "comprehensive"
}
```

## 📊 Response Format

All API responses follow a consistent structure:

### Success Response
```json
{
  "success": true,
  "data": {
    // Response data
  }
}
```

### Error Response
```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Human readable error message",
    "details": {
      // Additional error details
    }
  },
  "metadata": {
    "timestamp": "2024-12-19T10:30:00Z",
    "requestId": "req_12345678-90ab-cdef-1234-567890abcdef",
    "path": "/api/v1/endpoint"
  }
}
```

## 🎯 Key Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/health` | GET | System health check |
| `/api/v1/projects` | POST | Create new project |
| `/api/v1/projects/{id}` | GET | Get project details |
| `/api/v1/projects/{id}/research/start` | POST | Start AI research |
| `/api/v1/projects/{id}/clarification/questions` | GET | Get clarification questions |
| `/api/v1/projects/{id}/generate/prd` | POST | Generate PRD |
| `/api/v1/projects/{id}/export/markdown` | GET | Download PRD |
| `/api/v1/projects/{id}/search` | POST | Semantic search |

## 🔍 Advanced Features

### Semantic Search
- Search across documents, research findings, and clarifications
- AI-powered relevance scoring
- Contextual result snippets

### Document Analysis  
- Automatic feature extraction
- Requirement identification
- Technical specification parsing
- Content similarity matching

### Architecture Diagrams
- Mermaid-format diagram generation
- System architecture visualization
- Data flow diagrams
- Export to SVG, PNG, PDF

## 📝 Mock Data Examples

All YAML files include comprehensive mock data examples for:
- Request payloads with realistic product scenarios
- Response schemas with detailed field descriptions  
- Error responses with proper error codes
- Progressive workflow examples (project creation → research → clarification → PRD generation)

## 🛠️ Integration Notes

### SwaggerHub Features Supported
- ✅ OpenAPI 3.0.3 specification
- ✅ Complete schema definitions with examples
- ✅ Detailed parameter descriptions
- ✅ Response examples and error codes
- ✅ Security scheme definitions
- ✅ Tag-based endpoint organization
- ✅ Reusable components and references

### Best Practices Implemented
- Consistent error handling across all endpoints
- Proper HTTP status codes
- Detailed API documentation
- Request/response validation schemas
- Security considerations
- Rate limiting specifications

---

**Note**: These are mock API specifications designed for documentation and development planning. Actual implementation may vary based on technical requirements and architectural decisions.
